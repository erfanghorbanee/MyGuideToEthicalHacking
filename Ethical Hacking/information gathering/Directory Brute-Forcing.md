# Directory Brute-Forcing

## Dirsearch

```shell
./dirsearch.py -u scanme.nmap.org -e php
```

## Gobuster

Gobuster is a tool used to brute-force: URIs (directories and files) in web sites, DNS subdomains (with wildcard support), Virtual Host names on target web servers, Open Amazon S3 buckets, Open Google Cloud buckets and TFTP servers.

Gobuster is useful for pentesters, ethical hackers and forensics experts. It also can be used for security tests.

```shell
gobuster dir -u target_url -w wordlist
```

<https://www.kali.org/tools/gobuster/>

## Dirbuster

DirBuster is a multi threaded java application designed to brute force directories and files names on web/application servers.

<https://www.kali.org/tools/dirbuster/>

## EyeWitness

Manually visiting all the pages you’ve found through brute-forcing can be time-consuming. Instead, use a screenshot tool like EyeWitness (<https://github.com/FortyNorthSecurity/EyeWitness/>) or Snapper (<https://github.com/dxa4481/Snapper/>) to automatically verify that a page is hosted on each location.

EyeWitness accepts a list of URLs and takes screenshots of each page. In a photo gallery app, you can quickly skim these to find the interesting-looking ones. Keep an eye out for hidden services, such as developer or admin panels, directory listing pages, analytics pages, and pages that look outdated and ill maintained. These are all common places for vulnerabilities to manifest.
