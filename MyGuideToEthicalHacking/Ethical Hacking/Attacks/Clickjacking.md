# Clickjacking

## Countermeasure

![photo_2023-12-07 08.41.37.jpeg](../../../_resources/photo_2023-12-07%2008.41.37.jpeg)

## x-frame-options http response header

The X-Frame-Options HTTP response header is a security feature that helps to protect websites against clickjacking attacks. Clickjacking, also known as a UI redress attack, occurs when an attacker embeds a website or web application within an iframe on their own malicious site, tricking users into interacting with the embedded content unknowingly.

The X-Frame-Options header allows a web server to control whether a browser should be allowed to render a page in a frame or iframe. There are three possible values for this header:

**DENY:** The page cannot be displayed in a frame, regardless of the site attempting to do so.

```http
X-Frame-Options: DENY
```

**SAMEORIGIN:** The page can only be displayed in a frame on the same origin as the page itself. This means the page can be framed by other pages on the same domain but not by pages on different domains.

```http
X-Frame-Options: SAMEORIGIN
```

**ALLOW-FROM uri:** The page can only be displayed in a frame on the specified origin. This allows more flexibility by specifying the exact domain that is allowed to frame the content.

```http
X-Frame-Options: ALLOW-FROM https://example.com
```

Here's an example of how the X-Frame-Options header might appear in an HTTP response:

```http
HTTP/1.1 200 OK
Content-Type: text/html
X-Frame-Options: DENY
```

In this example, the server is instructing the browser not to allow the page to be displayed in any frame (DENY). This helps to prevent clickjacking attacks and enhances the security of the web application.

## frame-ancestors

The frame-ancestors directive is part of the Content Security Policy (CSP) standard, and it is used to control which web pages are allowed to embed a particular web page using iframes. Specifically, it specifies a list of permitted ancestors for the embedding.

The frame-ancestors directive can be set within the CSP header of an HTTP response to instruct the browser about the policy regarding framing of the content.

```http
Content-Security-Policy: frame-ancestors 'self' https://trusted-example.com;
```

In this example:

'self': Allows the page to be framed by other pages from the same origin (the current domain).

<https://trusted-example.com>: Allows the page to be framed by pages served from the specified domain.

This configuration essentially says that the content can only be embedded in iframes on pages that are part of the same origin or on pages served from the "<https://trusted-example.com>" domain.

It's a security measure designed to prevent clickjacking and similar attacks by controlling which domains are permitted to embed a particular page in iframes. If a page is loaded in an iframe on a disallowed domain, the browser will prevent the rendering of the content within that iframe, enhancing the security of the web application.

## frame busting

## tips

It's important to note that the use of frames has become obsolete, and iframes are still used but sparingly. Modern web development often relies on other techniques, such as AJAX, dynamic loading, and single-page applications (SPAs), to achieve similar results without the drawbacks associated with frames and iframes.
