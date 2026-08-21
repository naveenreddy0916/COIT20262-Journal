# COIT20262 Advanced Network Security — Week 4 Journal

**Student ID:** 12314045  
**Topic:** Symmetric Key Cryptography with OpenSSL

## Work completed

This week introduced practical cryptography using **OpenSSL** in a Linux virtual machine. I first checked the OpenSSL command groups with:

```bash
openssl help
```

The main practical task was **AES-256-CBC symmetric encryption**. A random secret key and a random initialisation vector (IV) were generated using OpenSSL. The important point was that the encryption operation used the actual key and IV values rather than a password.

The workflow followed was:

1. Generate a random AES secret key.
2. Generate a random IV.
3. Create a plaintext message file.
4. Encrypt the plaintext using AES-256-CBC.
5. Exchange the ciphertext with a partner.
6. Decrypt received ciphertext using the correct shared key and IV.
7. Store the practical files and evidence securely.

The OpenSSL random-generation operation used in the tutorial was based on:

```bash
openssl rand ...
```

The AES performance activity used:

```bash
openssl speed aes-256-cbc
```

The speed test demonstrated that AES can perform a very large number of operations per second, but exhaustive search of the **256-bit key space** remains computationally infeasible. This provided a practical reason for using sufficiently large cryptographic keys rather than relying only on algorithm speed.

## Assignment connection

The Week 4 work provided the basis for the symmetric component of **Assignment 1 Question 3**. For student ID `12314045`, the assignment requires a secret AES key and IV together with the plaintext and encrypted message files:

```text
12314045-key.txt
12314045-iv.txt
12314045-message.txt
12314045-message.enc
```

The key and IV must be protected because anyone who obtains both values can decrypt the AES ciphertext.

## Key learning

I learned the roles of the **secret key**, **IV**, plaintext and ciphertext in AES-CBC. Symmetric encryption is efficient, but secure key distribution is a major practical issue. This explains why public-key cryptography is used in the assignment to protect the AES key and IV before they are exchanged.
