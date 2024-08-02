# Firewall

Firewalls come in many forms, including hardware, software, or a combination. Their presence is vital, a cornerstone of any cyber security defence strategy. The following are the common types of firewalls that exist:

- Stateless/packet-filtering: This firewall provides the most straightforward functionality by inspecting and filtering individual network packets based on a set of rules that would point to a source or destination IP address, ports and protocols. The firewall doesn’t consider any context of each connection when making decisions and effectively blocks denial–of–service attacks and port scans.
- Stateful inspection: This firewall is more sophisticated. It is used to track the state of network connections and use this information to make filtering decisions. For example, if a packet being channelled to the network is part of an established connection, the stateful firewall will let it pass through. However, the packet will be blocked if it is not part of an established connection.
- Proxy service: This firewall protects the network by filtering messages at the application layer, providing deep packet inspection and more granular control over traffic content. The firewall can block access to certain websites or block the transmission of specific types of files.
- Web application firewall (WAF): This firewall is designed to protect web applications. WAFs block common web attacks such as SQL injection, cross-site scripting, and denial-of-service attacks.
- Next-generation firewall: This firewall combines the functionalities of the stateless, stateful, and proxy firewalls with features such as intrusion detection and prevention and content filtering.

## open-source firewalls

- pfSense: A widely used open-source firewall/router software that offers features like VPN, intrusion detection, and more.
- OPNsense: A fork of pfSense with a focus on more modern features and a different user interface.
- Smoothwall: Another open-source firewall solution with a focus on ease of use and web filtering.
