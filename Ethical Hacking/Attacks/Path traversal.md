## Path traversal

Path traversal is also known as directory traversal. These vulnerabilities enable an attacker to read arbitrary files on the server that is running an application. This might include:

- Application code and data.
- Credentials for back-end systems.
- Sensitive operating system files.

In some cases, an attacker might be able to write to arbitrary files on the server, allowing them to modify application data or behavior, and ultimately take full control of the server.

## Example

Imagine a shopping application that displays images of items for sale. This might load an image using the following HTML:

`<img src="/loadImage?filename=218.png">`

The loadImage URL takes a filename parameter and returns the contents of the specified file. The image files are stored on disk in the location /var/www/images/. To return an image, the application appends the requested filename to this base directory and uses a filesystem API to read the contents of the file. In other words, the application reads from the following file path:

`/var/www/images/218.png`
This application implements no defenses against path traversal attacks. As a result, an attacker can request the following URL to retrieve the /etc/passwd file from the server's filesystem:

`https://insecure-website.com/loadImage?filename=../../../etc/passwd`
This causes the application to read from the following file path:

/var/www/images/../../../etc/passwd
The sequence ../  is valid within a file path, and means to step up one level in the directory structure. The three consecutive ../ sequences step up from /var/www/images/ to the filesystem root, and so the file that is actually read is:
`/etc/passwd`

On Unix-based operating systems, this is a standard file containing details of the users that are registered on the server, but an attacker could retrieve other arbitrary files using the same technique.

On Windows, both ../ and ..\ are valid directory traversal sequences. The following is an example of an equivalent attack against a Windows-based server:

`https://insecure-website.com/loadImage?filename=..\..\..\windows\win.ini`

## passwd

The /etc/passwd file on Linux contains user account information. Each line in the file represents a user account and is divided into several fields separated by colons (:). The fields are as follows:

- Username: The first field is the username. In your example, you have entries like root, daemon, bin, etc.

- Password Placeholder: The second field traditionally held the encrypted password. However, in modern systems, this information is often stored in the /etc/shadow file for security reasons. In your example, you see x in this field, indicating that the password information is stored elsewhere.

- User ID (UID): The third field is the user ID, a unique numeric identifier for the user. The root user typically has a UID of 0.

- Group ID (GID): The fourth field is the primary group ID. It specifies the primary group for the user.

- User Info: The fifth field is the user's full name or other information about the user.

- Home Directory: The sixth field is the user's home directory. This is the directory where the user is placed after logging in.

- Login Shell: The seventh field is the user's login shell. It specifies the program that is started when the user logs in. Common shells include /bin/bash, /bin/sh, /bin/zsh, etc.

So, for example:

- The line root:x:0:0:root:/root:/bin/bash indicates that the root user has a UID and GID of 0, a home directory of /root, and uses the Bash shell as its login shell.

- The line for the user "peter" is peter:x:12001:12001::/home/peter:/bin/bash, which means that Peter has a UID and GID of 12001, a home directory of /home/peter, and uses Bash as the login shell.

- The line for the user "messagebus" is messagebus:x:101:101::/nonexistent:/usr/sbin/nologin, which means that the messagebus user has a UID and GID of 101, a home directory of /nonexistent, and uses /usr/sbin/nologin as the login shell.

**Note:** The information in the /etc/passwd file is read-only, and user passwords are typically stored in the /etc/shadow file for security reasons. The x in the password field indicates that the password is stored in the shadow file.
