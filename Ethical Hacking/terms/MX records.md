# MX records

MX records, short for Mail Exchange records, are a type of data in the Domain Name System (DNS) that specifies a mail server responsible for accepting email messages on behalf of a recipient's domain. Each MX record points to a mail server and also contains a priority setting which is used to determine the order in which mail servers should be tried.

When an email is sent, the sender's email server uses the DNS to look up the MX records for the recipient's domain. The MX records provide the names of the servers that can handle email for the domain, and the priority value helps to direct the email to the primary server first, or to backup servers if the primary is not available. The lower the priority number, the higher the preference for that server.

MX records make it possible to direct email to a domain's mail servers even if they are hosted on different physical servers or with different service providers, ensuring that email can be reliably delivered to the intended recipients.
