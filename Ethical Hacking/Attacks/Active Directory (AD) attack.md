## Definition:

An Active Directory (AD) attack is a type of cyberattack that targets Microsoft's Active Directory service, a centralized authentication and authorization service used in Windows environments. Active Directory is a crucial component in many organizations, as it manages user accounts, security policies, and access control within a network. When an attacker successfully exploits vulnerabilities or weaknesses in Active Directory, they can gain unauthorized access, compromise user accounts, and potentially take control of the entire network.

## Common types of Active Directory attacks:

**Password Attacks:** Attackers may use various techniques like brute force attacks, dictionary attacks, or password spraying to crack or guess user passwords, gaining unauthorized access to user accounts.

**Pass-the-Hash (PtH) Attack:** In a PtH attack, attackers steal password hashes from a compromised system and use them to authenticate as users on other systems without needing to know the actual passwords.

**Pass-the-Ticket (PtT) Attack:** Similar to PtH, PtT attacks involve the theft and use of Kerberos tickets to impersonate users and gain unauthorized access to systems.

**Kerberoasting:** Attackers target service accounts in Active Directory to extract their Kerberos tickets and then attempt to crack these tickets offline to gain unauthorized access to systems or services.

**Golden Ticket Attack:** An attacker who successfully compromises Active Directory may forge a "Golden Ticket" Kerberos ticket that grants them unlimited access to any resource in the domain.

**Silver Ticket Attack:** In a Silver Ticket attack, an attacker forges a Kerberos ticket for a specific service, allowing them to access that service without needing valid credentials.

**Overpass-the-Hash Attack:** Attackers manipulate Active Directory objects to reset passwords and potentially take control of user accounts.

**Abusing Active Directory Trust Relationships:** If an organization has multiple Active Directory domains or forests, attackers may exploit trust relationships between them to move laterally within the network.

**Domain Enumeration:** Attackers use various techniques to gather information about the domain's structure, user accounts, and system configurations. This information helps them plan more targeted attacks.

**Distributed Denial of Service (DDoS) Attacks:** While not always specific to Active Directory, DDoS attacks can disrupt Active Directory services and impact network availability.

It's important to note that Active Directory attacks are often part of a broader attack strategy, such as a network intrusion or data breach. Organizations must implement robust security measures, regularly update and patch their systems, and monitor their network for unusual activity to protect against these types of attacks. Additionally, training and awareness programs can help educate employees about security best practices to prevent social engineering attacks that may lead to unauthorized access.