# WebSocket Vulnerabilities

While WebSockets can boost performance, they also come with security risks that developers need to monitor. Since WebSocket connections stay open and active, they can be taken advantage of if the proper security measures aren't in place.

Here are some common vulnerabilities:

**Weak Authentication and Authorisation**: Unlike regular HTTP, WebSockets don't have built-in ways to handle user authentication or session validation. If you don't set these controls up properly, attackers could slip in and get access to sensitive data or mess with the connection.

**Message Tampering**: WebSockets let data flow back and forth constantly, which means attackers could intercept and change messages if encryption isn't used. This could allow them to inject harmful commands, perform actions they shouldn't, or mess with the sent data.

**Cross-Site WebSocket Hijacking (CSWSH)**: This happens when an attacker tricks a user's browser into opening a WebSocket connection to another site. If successful, the attacker might be able to hijack that connection or access data meant for the legitimate server.

**Denial of Service (DoS)**: Because WebSocket connections stay open, they can be targeted by DoS attacks. An attacker could flood the server with a ton of messages, potentially slowing it down or crashing it altogether.
