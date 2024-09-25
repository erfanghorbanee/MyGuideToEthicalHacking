# John the Ripper

John the Ripper is a fast password cracker which supports hundreds of hash and cipher types, and runs on many operating systems, CPUs, GPUs, and even some FPGAs.

## Scenario

Let's say you have an SSH private key that is password-protected and you want to attempt to crack the password using John the Ripper, follow these steps:

### Convert the SSH Private Key to a John-friendly Format

John the Ripper cannot directly read SSH private keys in their original format, so you need to convert the key into a format that John can understand using the ssh2john utility(included in the John the Ripper package).

```shell
python3 /path/to/ssh2john.py /path/to/id_rsa > ssh_hash.txt

```

### Crack the Password with John the Ripper

Run John the Ripper against the generated hash:

```shell
john ssh_hash.txt --wordlist=/path/to/wordlist.txt
```

### Final steps

#### Ensure Proper Permissions

First, make sure your private key file has the correct permissions. The file should only be readable by you:

```shell
chmod 600 /path/to/id_rsa
```

**Note:** When using SSH, the SSH client on your machine performs a security check to ensure that your private key file is not accessible by others. If the permissions are too open, SSH will refuse to use the key, and you'll get an error.

#### Use the SSH Command with the Private Key

Use the following command to connect to the remote server using your private key:

```shell
ssh -i /path/to/id_rsa username@remote_host
```
