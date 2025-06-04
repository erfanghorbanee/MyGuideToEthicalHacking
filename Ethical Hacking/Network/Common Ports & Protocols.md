# Common Ports & Protocols

![ecfa565ac79f085688f3d990339d3352.png](../../_resources/ecfa565ac79f085688f3d990339d3352.png)

## SSL

SSL (Secure Sockets Layer) was replaced by TLS due to various vulnerabilities. When you hear "SSL" it usually means "TLS" nowadays (sometimes people say "SSL/TLS" out of habit).

TLS is actively maintained and developed.

SSL protocols themselves are deprecated and should not be used.

## TLS

An upgrade to SSL.

Like SSL, its predecessor, TLS is a cryptographic protocol operating at the OSI model’s transport layer. It allows secure communication between a client and a server over an insecure network. ensuring confidentiality and integrity. TLS ensures that no one can read or modify the exchanged data.

### Examples

HTTP, DNS, MQTT, and SIP, which have become HTTPS, DoT (DNS over TLS), MQTTS, and SIPS, where the appended “S” stands for Secure due to the use of SSL/TLS.

## SMTP, POP3, IMAP

All relates to mail.

POP3, SMTP, and IMAP become POP3S, SMTPS, and IMAPS, where the appended “S” stands for Secure.

## Telnet vs SSH

SSH is the encrypted version of telnet.

## SMB

SMB (Server Message Block) is a network protocol used for sharing files, printers, and other resources between computers on a network. It allows systems, typically within a local network, to communicate and access shared files or services. SMB is commonly found on Windows systems but can also be implemented on other operating systems.

**As a pentester, you're gonna see this alot.**

## DNS

is both tcp and udp protocol.

## SFTP, FTPS

SFTP stands for SSH File Transfer Protocol and allows secure file transfer. It is part of the SSH protocol suite and shares the same port number, 22.

If enabled in the OpenSSH server configuration, you can connect using a command such as sftp username@hostname. Once logged in, you can issue commands such as `get filename` and `put filename` to download and upload files, respectively.

SFTP should not be confused with FTPS. FTPS stands for File Transfer Protocol Secure. While FTP uses port 21, FTPS usually uses port 990. It requires certificate setup, and it can be tricky to allow over strict firewalls as it uses separate connections for control and data transfer.

Setting up an SFTP server is as easy as enabling an option within the OpenSSH server. Like HTTPS, SMTPS, POP3S, IMAPS, and other protocols that rely on TLS for security, FTPS requires a proper TLS certificate to run securely.
