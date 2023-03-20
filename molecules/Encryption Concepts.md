### Summary of Encryption
Encrypt is a way of scrambling data so that only authorized parties understand it. #secure 


### Encryption Details
There are two types of encryption: symmetric and asymmetric.
**Symmetric Keys** 
> Shared key to encrypt and decrypt the data. e.g. session key between an authenticated server and browser

**Asymmetric Keys**
>Public key and private keys. Public key is used by the public to encrypt the data and is sent over an unsecured network. The server uses a secret private key
>The use of a private key to sign a message is a crucial component of many security protocols, such as SSL/TLS, S/MIME, and [[PGP]], as well as digital certificates and other forms of digital identity verification.

**Cypher**
> Is the encryption algorithm itself.
> [[AES]] (Advanced Encryption Standard): Symmetric Key Encryption.
>[[RSA]] (Rivest-Shamir-Adleman): Asymmetric Key Encryption.
 >[[Diffie-Hellman]]: Key exchange protocol

 **Key Material**
>The actual secret key or keys used in a cryptographic system to encrypt and decrypt data

> **Client-Side Encryption**
- Server can never decrypt.
- Server should never be able to decrypt.
- Envelop encryption.

> Envelop Encryption



---
> **References for Encryption**
> 1.  https://www.cloudflare.com/learning/ssl/what-is-encryption/
> 
 
*Created on 2023-03-19 15:23*