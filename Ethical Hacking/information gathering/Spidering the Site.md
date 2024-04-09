# Spidering the Site

Another way of discovering directories and paths is through web spidering, or web crawling, a process used to identify all pages on a site. A web spider tool starts with a page to visit. It then identifies all the URLs embedded on the page and visits them. By recursively visiting all URLs found on all pages of a site, the web spider can uncover many hidden endpoints in an application.

OWASP Zed Attack Proxy (ZAP) at <https://www.zaproxy.org/> has a built-in web spider you can use (Figure 5-2). This open source security tool includes a scanner, proxy, and many other features. Burp Suite has an equivalent tool called the crawler, but I prefer ZAP’s spider.
