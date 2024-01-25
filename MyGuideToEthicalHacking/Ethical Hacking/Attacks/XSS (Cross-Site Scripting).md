# XSS (Cross-Site Scripting)

## Stored XSS

![de121f1e20d0be59a83001b2b660a010.png](../../../_resources/de121f1e20d0be59a83001b2b660a010.png)
![879002ecf47223f3661ad79b35694869.png](../../../_resources/879002ecf47223f3661ad79b35694869.png)

## Blind XSS

![cacb62839cdf27bb1c22a1d6d5591d86.png](../../../_resources/cacb62839cdf27bb1c22a1d6d5591d86.png)

## DOM XSS

![5988fa858f3a55cba91fa1e28c1eff30.png](../../../_resources/5988fa858f3a55cba91fa1e28c1eff30.png)
![8fe84f996fe9cffc8b8c29ded531b57d.png](../../../_resources/8fe84f996fe9cffc8b8c29ded531b57d.png)

## Reflected XSS

![7e3801221242f238189434c391180842.png](../../../_resources/7e3801221242f238189434c391180842.png)
![58fee3636d49604bb939afcc136cb39e.png](../../../_resources/58fee3636d49604bb939afcc136cb39e.png)

## Self XSS

![05c6bae344b51dac2853aa2d9d7eb1ac.png](../../../_resources/05c6bae344b51dac2853aa2d9d7eb1ac.png)

## Impacts

![8f19f7a37f33c291337666183f591398.png](../../../_resources/8f19f7a37f33c291337666183f591398.png)

## Countermeasures

![de81ce40170cf42621d7f543c568246b.png](../../../_resources/de81ce40170cf42621d7f543c568246b.png)

## X-XSS-Protection HTTP header

The X-XSS-Protection HTTP header is a security feature that helps to mitigate the risk of cross-site scripting (XSS) attacks in web applications. XSS attacks occur when an attacker injects malicious scripts into web pages that are viewed by other users. The X-XSS-Protection header allows web developers to enable or disable the built-in XSS protection mechanisms provided by modern web browsers.

Here's how the X-XSS-Protection header works:

When a web browser receives a response from a server, it checks for the presence of the X-XSS-Protection header.

If the header is present and set to a specific value, the browser's XSS filter is activated.

The XSS filter analyzes the content of the web page for potential XSS attacks.

If the filter detects suspicious scripts, it may either sanitize the content by removing the malicious script or block the entire page from rendering.

If the X-XSS-Protection header is not present or is set to a specific value indicating that the filter should be disabled, the browser won't perform XSS filtering.

Example of setting the X-XSS-Protection header in an HTTP response:

```
HTTP/1.1 200 OK
Content-Type: text/html; charset=utf-8
X-XSS-Protection: 1; mode=block
```

**Explanation of the example:**

X-XSS-Protection: 1; mode=block: This header enables the XSS filter (1) and instructs the browser to block the rendering of the page if a potential XSS attack is detected (mode=block).

mode=block is a common value used to ensure that the browser takes strict action when it encounters a suspected XSS attack.

Developers can also customize the X-XSS-Protection header based on their security requirements. For example:

X-XSS-Protection: 1; report=<https://example.com/report-xss> would enable the filter and send a report to the specified URL when a potential XSS attack is detected.

X-XSS-Protection: 0 would disable the XSS filter.

It's important to note that while the X-XSS-Protection header provides an additional layer of defense, developers should not solely rely on it for preventing XSS attacks. Secure coding practices, input validation, and other security measures are essential components of a comprehensive security strategy.


## XSS Hunter Express

An easy-to-setup version of XSS Hunter. Sets up in five minutes and requires no maintenance!
https://github.com/mandatoryprogrammer/xsshunter-express

## XSS Payloads
https://github.com/nettitude/xss_payloads
https://github.com/payloadbox/xss-payload-list