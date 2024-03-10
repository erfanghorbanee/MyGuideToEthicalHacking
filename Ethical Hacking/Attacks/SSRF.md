# SSRF

SSRF, or server-side request forgery, is a security vulnerability that occurs when an attacker tricks a web application into making unauthorised requests to internal or external resources on the server's behalf. This can allow an attacker to interact with internal systems, potentially leading to data exposure or unauthorised actions. Leaving web applications vulnerable to SSRF can have profound security implications, potentially leading to unauthorised access to internal systems, remote code execution (RCE), data breaches, or the application being further compromised.

## Types of SSRF Attack
- Basic: In a basic SSRF attack, the attacker sends a crafted request from the vulnerable server to internal or external resources. For example, they might attempt to access files on the local file system, internal services, or databases that are not intended to be publicly accessible.
- Blind SSRF: In a blind SSRF attack, the attacker doesn't directly see the response to the request. Instead, they may infer information about the internal network by measuring the time it takes for the server to respond or observing error message changes.
- Semi-blind SSRF: In semi-blind SSRF, again, the attacker does not receive direct responses in their browser or application. However, they rely on indirect clues, side-channel information, or observable effects within the application to determine the success or failure of their SSRF requests. This might involve monitoring changes in application behaviour, response times, error messages, and other signs.

## Prerequisites for Exploitation

Vulnerable input points: Web applications must have input fields susceptible to manipulation, such as URLs or file upload functionalities.
Lack of input validation: The application should have adequate input validation or effective sanitisation mechanisms, allowing an attacker 
to craft malicious requests.

## How Does SSRF Work?

- Identifying vulnerable input: The attacker locates an input field within the application that can be manipulated to trigger server-side requestsImage for how SSRF works. This could be a URL parameter in a web form, an API endpoint, or request parameter input such as the referrer.
- Manipulating the input: The attacker inputs a malicious URL or other payloads that cause the application to make unintended requests. This input could be a URL pointing to an internal server, a loopback address, or an external server under the attacker's control.
- Requesting unauthorised resources: The application server, unaware of the malicious input, makes a request to the specified URL or resource. This request could target internal resources, sensitive services, or external systems.
- Exploiting the response: Depending on the application's behaviour and the attacker's payload, the response from the malicious request may provide valuable information, such as internal server data, credentials, system credentials/information, or pathways for further exploitation.

## Mitigation Measures
To prevent SSRF exploitation, the following mitigations are suggested:

- Employing strict input validation and sanitisation to prevent malicious input.
- Using allow lists to control which domains and IPs the application can access.
- Applying network segmentation to restrict requests to authorised resources.
- Following the principle of least privilege, granting the minimum permissions required for system operations.
