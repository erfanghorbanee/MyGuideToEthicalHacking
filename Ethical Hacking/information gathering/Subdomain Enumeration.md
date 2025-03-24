# Subdomain Enumeration

## Gobuster

Gobuster is a tool for brute-forcing to discover subdomains, directories, and files on target web servers. Its DNS mode is used for subdomain brute-forcing. In this mode, you can use the flag -d to specify the domain you want to brute-force and -w to specify the wordlist you want to use:

```shell
gobuster dns -d target_domain -w wordlist
```
