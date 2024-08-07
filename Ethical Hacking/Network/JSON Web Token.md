# JSON Web Token

The JSON Web Token (JWT) is one of the most commonly used types of authentication tokens. It has three components: **a header, a payload, and a signature.**

The header identifies the algorithm used to generate the signature. It’s a base64url-encoded string containing the algorithm name. Here’s what a JWT header looks like:
`eyBhbGcgOiBIUzI1NiwgdHlwIDogSldUIH0K`

This string is the base64url-encoded version of this text:
`{ "alg" : "HS256", "typ" : "JWT" }`

The payload section contains information about the user’s identity. This section, too, is base64url encoded before being used in the token. Here’s an example of the payload section, which is the base64url-encoded string of { "user_name" : "admin", }:
`eyB1c2VyX25hbWUgOiBhZG1pbiB9Cg`

Finally, the signature section validates that the user hasn’t tampered with the token. It’s calculated by concatenating the header with the payload, then signing it with the algorithm specified in the header, and a secret key. Here’s what a JWT signature looks like:
`4Hb/6ibbViPOzq9SJflsNGPWSk6B8F6EqVrkNjpXh7M`

For this specific token, the signature was generated by signing the
string `eyBhbGcgOiBIUzI1NiwgdHlwIDogSldUIH0K.eyB1c2VyX25hbWUgOiBhZG1pbiB9Cg` with the HS256 algorithm using the secret key key. The complete token concatenates each section (the header, payload, and signature), separating them with a period (.):

```bash
eyBhbGcgOiBIUzI1NiwgdHlwIDogSldUIH0K.eyB1c2VyX25hbWUgOiBhZG1pbiB9Cg.4Hb/6ibbViPOzq9SJflsNGPWSk6B8F6EqVrkNjpXh7M
```

When implemented correctly, JSON web tokens provide a secure way to identify the user. When the token arrives at the server, the server can verify that the token has not been tampered with by checking that the signature is correct. Then the server can deduce the user’s identity by using the information contained in the payload section. And since the user does not have access to the secret key used to sign the token, they cannot alter the payload and sign the token themselves.

## Manipulating the alg Field

Sometimes applications fail to verify a token’s signature after it arrives at the server. This allows an attacker to simply bypass the security mechanism by providing an invalid or blank signature.
One way that attackers can forge their own tokens is by tampering with the alg field of the token header, which lists the algorithm used to encode the signature. If the application does not restrict the algorithm type used in the JWT, an attacker can specify which algorithm to use, which could compromise the security of the token.
JWT supports a none option for the algorithm type. If the alg field is set to none, even tokens with empty signature sections would be considered valid.
Consider, for example, the following token:
`eyAiYWxnIiA6ICJOb25lIiwgInR5cCIgOiAiSldUIiB9Cg.eyB1c2VyX25hbWUgOiBhZG1pbiB9Cg.`

This token is simply the base64url-encoded versions of these two blobs, with no signature present:
`{ "alg" : "none", "typ" : "JWT" } { "user" : "admin" }`

This feature was originally used for debugging purposes, but if not
turned off in a production environment, it would allow attackers to forge any token they want and impersonate anyone on the site.
Another way attackers can exploit the alg field is by changing the type of algorithm used. The two most common types of signing algorithms used for JWTs are HMAC and RSA. HMAC requires the token to be signed with a key and then later verified with the same key. When using RSA, the token would first be created with a private key, then verified with the corresponding public key, which anyone can read. It is critical that the secret key for HMAC tokens and the private key for RSA tokens be kept a secret.

Now let’s say that an application was originally designed to use RSA
tokens. The tokens are signed with a private key A, which is kept a secret from the public. Then the tokens are verified with public key B, which is available to anyone. This is okay as long as the tokens are always treated as RSA tokens. Now if the attacker changes the alg field to HMAC, they might be able to create valid tokens by signing the forged tokens with the RSA public key, B. When the signing algorithm is switched to HMAC, the token is still verified with the RSA public key B, but this time, the token can be signed with the same public key too.

## Brute-Forcing the Key

It could also be possible to guess, or brute-force, the key used to sign a JWT. The attacker has a lot of information to start with: the algorithm used to sign the token, the payload that was signed, and the resulting signature.

## Reading Sensitive Information

Since JSON web tokens are used for access control, they often contain information about the user. If the token is not encrypted, anyone can base64-decode the token and read the token’s payload. If the token contains sensitive information, it might become a source of information leaks.

A properly implemented signature section of the JSON web token provides data integrity, not confidentiality. This is why it's advised not to store sensitive information in a JWT unless the entire token is encrypted using additional mechanisms, such as **JSON Web Encryption (JWE)**.

## Other Terms

- **JWS (JSON Web Signature)**: Sign JSON data to ensure integrity and authenticity.

- **JWE (JSON Web Encryption)**: Encrypt JSON data for confidentiality.
- **JWA (JSON Web Algorithms)**: Defines cryptographic algorithms for JWS, JWE, and JWT.
- **JWK (JSON Web Key)**: Standard format for representing cryptographic keys.

A JWT  can be:

- **JWS**: A signed JWT ensuring data integrity and authenticity.
- **JWE**: An encrypted JWT ensuring data confidentiality.

![jwt.png](../../_resources/jwt.png)

In short, JWT leverages JWS, JWE, JWA, and JWK to securely transmit and verify data.
