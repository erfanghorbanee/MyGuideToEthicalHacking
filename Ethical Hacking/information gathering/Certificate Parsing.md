# Certificate Parsing

Another way of finding hosts is to take advantage of the Secure Sockets Layer (SSL) certificates used to encrypt web traffic. An SSL certificate’s Subject Alternative Name field lets certificate owners specify additional hostnames that use the same certificate, so you can find those hostnames by parsing this field. Use online databases like crt.sh, Censys, and Cert Spotter to find certificates for a domain.

For example, by running a certificate search using crt.sh for facebook.com, we can find Facebook’s SSL certificate. You’ll see that that many other domain names belonging to Facebook are listed.

<https://crt.sh/?q=facebook.com&exclude=expired&group=none>
