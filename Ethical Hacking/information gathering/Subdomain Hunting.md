# Subdomain Hunting

## Certificates

Another way of finding hosts is to take advantage of the Secure Sockets Layer (SSL) certificates used to encrypt web traffic. An SSL certificate’s Subject Alternative Name field lets certificate owners specify additional hostnames that use the same certificate, so you can find those hostnames by parsing this field. Use online databases like [crt.sh](https://crt.sh/), Censys, and Cert Spotter to find certificates for a domain.

For example, by running a certificate search using `crt.sh` for facebook.com, we can find Facebook’s SSL certificate. You’ll see that many other domain names belonging to Facebook are listed.

<https://crt.sh/?q=facebook.com&exclude=expired&group=none>

or for tryhackme website:

<https://crt.sh/?q=tryhackme.com>

## Search Engines

Search engines contain trillions of links to more than a billion websites, which can be an excellent resource for finding new subdomains. Using advanced search methods on websites like Google, such as the site: filter, can narrow the search results. For example, `site:*.domain.com -site:www.domain.com` would only contain results leading to the domain name domain.com but exclude any links to `www.domain.com`; therefore, it shows us only subdomain names belonging to `domain.com`.

## Tools

- Sublist3r (you can use `-t` to add more threads and get the result faster)  
    `sublist3r -d tesla.com`
- Amass(stronger)
- httprobe(Take a list of domains and probe for working HTTP and HTTPS servers)
- Gobuster  
    `gobuster dns -d target_domain -w wordlist`
- dnsrecon  
    `dnsrecon -t brt -d acmeitsupport.thm`

## Virtual Hosts

Some subdomains aren't always hosted in publically accessible DNS results, such as development versions of a web application or administration portals. Instead, the DNS record could be kept on a private DNS server or recorded on the developer's machines in their `/etc/hosts` file (or `c:\windows\system32\drivers\etc\hosts` file for Windows users), which maps domain names to IP addresses.

Because web servers can host multiple websites from one server when a website is requested from a client, the server knows which website the client wants from the Host header. We can utilize this host header by making changes to it and monitoring the response to see if we've discovered a new website.

Like with DNS Bruteforce, we can automate this process by using a wordlist of commonly used subdomains.

**ffuf**
```ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.10.99.130```

The above command uses the `-w` switch to specify the wordlist we are going to use. The `-H` switch adds/edits a header (in this instance, the Host header), we have the FUZZ keyword in the space where a subdomain would normally go, and this is where we will try all the options from the wordlist.

Because the above command will always produce a valid result, we need to filter the output. We can do this by using the page size result with the `-fs` switch. Edit the below command replacing `{size}` with the most occurring size value from the previous result and try it.

```ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.10.99.130 -fs {size}```

The `-fs` switch tells ffuf to ignore any results that are of the specified size.
