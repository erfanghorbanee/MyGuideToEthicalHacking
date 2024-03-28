# URL Encoding

URL encoding, also known as percent-encoding, is a mechanism for encoding information in a Uniform Resource Locator (URL) under certain circumstances.

The purpose of URL encoding is to encode certain characters that are not allowed in a URL, or which could cause ambiguity about a URL's interpretation. This includes characters such as spaces, certain symbols, and non-ASCII characters.

Characters are encoded by replacing them with a percent sign (%) followed by two hexadecimal digits that represent the ASCII code of the character. For example, the space character is encoded as `%20`.

## Example

Consider a URL that includes a query string with spaces and special characters:

Original string: `Hello World! How are you?`

If this string were part of a URL, specifically in the query part (after the `?`), it would be URL-encoded as:

Encoded string: `Hello%20World%21%20How%20are%20you%3F`

Here, the space characters have been replaced with `%20`, the exclamation mark (`!`) with `%21`, and the question mark (`?`) with `%3F`. This ensures that the URL is syntactically valid and interpretable by web servers and browsers.


Read more here:
https://www.w3schools.com/tags/ref_urlencode.ASP