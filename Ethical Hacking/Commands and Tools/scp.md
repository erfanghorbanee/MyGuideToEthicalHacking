# scp

The scp (Secure Copy Protocol) command is used to securely transfer files between two computers over a network. It uses SSH (Secure Shell) to encrypt the transfer, ensuring that the data remains secure during transmission. You can use scp to copy files from your local machine to a remote server, from a remote server to your local machine, or even between two remote servers.

for example, you can use this to share linpeas.sh file to a linux server and perform privilage escalation or any other attack scenario.

## example

This command sends a file from your local machine to a remote server:

```shell
scp /path/to/local/file username@remote_host:/path/to/remote/directory
```
