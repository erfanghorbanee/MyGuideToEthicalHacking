# Brute Force

## Generating Password List with Crunch

```shell
crunch 3 3 0123456789ABCDEF -o 3digits.txt
```

The command above specifies the following:

- 3 the first number is the minimum length of the generated password
- 3 the second number is the maximum length of the generated password
- 0123456789ABCDEF is the character set to use to generate the passwords
- \-o 3digits.txt saves the output to the 3digits.txt file

## Generating Custom Password List with CeWL

CeWL (pronounced "cool") is a custom word list generator tool that spiders websites to create word lists based on the site's content. Spidering, in the context of web security and penetration testing, refers to the process of automatically navigating and cataloguing a website's content, often to retrieve the site structure, content, and other relevant details. This capability makes CeWL especially valuable to penetration testers aiming to brute-force login pages or uncover hidden directories using organisation-specific terminology.

Beyond simple wordlist generation, CeWL can also compile a list of email addresses or usernames identified in team members' page links. Such data can then serve as potential usernames in brute-force operations.

To create and save a basic wordlist to a file, you can use the command below:

```shell
cewl http://MACHINE_IP -w output.txt
```

## Generating Valid Username List with ffuf

Website error messages are great resources for collating this information to build our list of valid usernames. Let's say we have a form to create a new user account if we go to some website's signup page.

If you try entering the username admin and fill in the other form fields with fake information, you'll see we get the error An account with this username already exists. We can use the existence of this error message to produce a list of valid usernames already signed up on the system by using the `ffuf` tool below. The ffuf tool uses a list of commonly used usernames to check against for any matches.

```ffuf -w /usr/share/wordlists/SecLists/Usernames/Names/names.txt -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u {base_url}/signup -mr "username already exists"```

In the above example, the `-w` argument selects the file's location on the computer that contains the list of usernames that we're going to check exists. The `-X` argument specifies the request method, this will be a `GET` request by default, but it is a `POST` request in our example. The ‍`-d` argument specifies the data that we are going to send. In our example, we have the fields username, email, password and cpassword. We've set the value of the username to FUZZ. In the ffuf tool, the `FUZZ` keyword signifies where the contents from our wordlist will be inserted in the request. The `-H` argument is used for adding additional headers to the request. In this instance, we're setting the `Content-Type` so the web server knows we are sending form data. The `-u` argument specifies the URL we are making the request to, and finally, the `-mr` argument is the text on the page we are looking for to validate we've found a valid username.

Using the valid_usernames.txt file we generated in the previous step, we can now use this to attempt a brute force attack on the login page.

## Attacking with ffuf

When running this command, make sure the terminal is in the same directory as the valid_usernames.txt file.

```ffuf -w valid_usernames.txt:W1,/usr/share/wordlists/SecLists/Passwords/Common-Credentials/10-million-password-list-top-100.txt:W2 -X POST -d "username=W1&password=W2" -H "Content-Type: application/x-www-form-urlencoded" -u {base_url}/login -fc 200```

This ffuf command is a little different to the previous one. Previously we used the `FUZZ` keyword to select where in the request the data from the wordlists would be inserted, but because we're using multiple wordlists, we have to specify our own FUZZ keyword. In this instance, we've chosen `W1` for our list of valid usernames and `W2` for the list of passwords we will try. The multiple wordlists are again specified with the `-w` argument but separated with a comma.  For a positive match, we're using the `-fc` argument to check for an HTTP status code other than `200`.

### Why Filter Out 200?

In many login systems:

When you enter invalid credentials, the server often returns HTTP 200 OK and simply reloads the page with an error message like “Invalid username or password.”

When you enter valid credentials, the server usually responds with a different status code, such as:

- 302 Redirect (to take you to a logged-in dashboard),
- 403 Forbidden, or
- even 500+ errors if the app misbehaves after a successful login attempt (rare but possible).

## Attacking with Hydra

### Simple example

```shell
hydra -l jan -P /usr/share/wordlists/rockyou.txt ssh://10.10.150.40
```

### Advanced example

```shell
hydra -l '' -P 3digits.txt -f -v MACHINE_IP http-post-form "/login.php:pin=^PASS^:Access denied" -s 8000
```

The command above will try one password after another in the 3digits.txt file. It specifies the following:

- \-l '' indicates that the login name is blank as the security lock only requires a password
- \-P 3digits.txt specifies the password file to use
- \-f stops Hydra after finding a working password
- \-v provides verbose output and is helpful for catching errors
- MACHINE_IP is the IP address of the target
- http-post-form specifies the HTTP method to use
- "/login.php:pin=^PASS^:Access denied" has three parts separated by :

1. /login.php is the page where the PIN code is submitted
2. pin=^PASS^ will replace ^PASS^ with values from the password list
3. Access denied indicates that invalid passwords will lead to a page that contains the text “Access denied”

- \-s 8000 indicates the port number on the target

## Attacking with wfuzz

`wfuzz -c -z file,usernames.txt -z file,passwords.txt --hs "Please enter the correct credentials" -u http://MACHINE_IP/login.php -d "username=FUZZ&password=FUZ2Z"`

In the command above:

- \-z file,usernames.txt loads the usernames list.
- \-z file,passwords.txt uses the password list generated by CeWL.
- \--hs "Please enter the correct credentials" hides responses containing the string "Please enter the correct credentials", which is the message displayed for wrong login attempts.
- \-u specifies the target URL.
- \-d "username=FUZZ&password=FUZ2Z" provides the POST data format where FUZZ will be replaced by usernames and FUZ2Z by passwords.
