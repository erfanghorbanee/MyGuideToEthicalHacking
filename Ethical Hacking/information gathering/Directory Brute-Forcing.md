# Directory Brute-Forcing

You can use Dirsearch or Gobuster for directory brute-forcing.

example:

```shell
./dirsearch.py -u scanme.nmap.org -e php
```

```shell
gobuster dir -u target_url -w wordlist
```

Manually visiting all the pages you’ve found through brute-forcing can be time-consuming. Instead, use a screenshot tool like EyeWitness (<https://github.com/FortyNorthSecurity/EyeWitness/>) or Snapper (<https://github.com/dxa4481/Snapper/>) to automatically verify that a page is hosted on each location.

EyeWitness accepts a list of URLs and takes screenshots of each page. In a photo gallery app, you can quickly skim these to find the interesting-looking ones. Keep an eye out for hidden services, such as developer or admin panels, directory listing pages, analytics pages, and pages that look outdated and ill maintained. These are all common places for vulnerabilities to manifest.
