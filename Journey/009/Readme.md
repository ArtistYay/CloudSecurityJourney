![placeholder image](Journey/006/assets/TCP_3.png)

# TLS and SSL

Secure Sockets Layer (SSL) and its successor, Transport Layer Security (TLS), are cryptographic protocols that safeguard online communication by encrypting data transmitted between a computer and a server. These protocols play a crucial role in protecting sensitive information, such as login credentials, financial data, and personal information, from interception and unauthorized access.

# Secure Sockets Layer (SSL)

Employs a combination of symmetric and asymmetric encryption techniques, along with digital certificates, to create a secure connection between a web browser and a server.

# Transport Layer Security (TLS)

TLS emerged as an enhanced iteration of SSL, addressing the vulnerabilities of its predecessor. TLS 1.0 marked the initial upgrade, followed by subsequent versions, with TLS 1.3 being the current standard. TLS offers a more robust and adaptable security framework, ensuring the confidentiality and integrity of data transmitted online.

# Symmetric encryption

Symmetric encryption, also known as private-key encryption, employs a single key for both encryption and decryption. This key is shared between the client and the server, ensuring that only authorized parties can exchange data securely. Symmetric encryption is highly efficient, making it ideal for encrypting large amounts of data.

## Examples

- **AES (Advanced Encryption Standard)**: AES is the most widely used symmetric encryption algorithm today. It is a block cipher that uses a 128-bit, 192-bit, or 256-bit key to encrypt and decrypt data. AES is very fast and secure, and it is used in a variety of applications, including Wi-Fi security, file encryption, and VPNs.

- **DES (Data Encryption Standard)**: DES was a popular symmetric encryption algorithm in the 1980s and 1990s, but it is no longer considered to be secure because it is vulnerable to brute-force attacks. DES is still used in some legacy applications, but it has been largely replaced by AES and other more modern algorithms.

- **Blowfish**: Blowfish is another popular symmetric encryption algorithm that is known for its speed and efficiency. Blowfish is a variable-key-length cipher, which means that it can use a key of any length from 32 to 448 bits. Blowfish is often used in applications where speed is important, such as file encryption and email security.

# Asymmetric encryption

Asymmetric encryption, also known as public-key encryption, utilizes a pair of keys: a public key and a private key. The public key is widely distributed, while the private key is kept confidential. Asymmetric encryption is used for secure key exchange, enabling the establishment of a shared symmetric key without transmitting it directly over the network.

## Examples

- **RSA (Rivest–Shamir–Adleman)**: RSA is one of the most widely used asymmetric encryption algorithms. It is based on the difficulty of factoring large prime numbers. RSA is used in a variety of applications, including digital signatures, secure file transfer, and VPNs.

- **DH (Diffie-Hellman)**: Diffie-Hellman is a key agreement protocol that allows two parties to establish a shared secret key over an insecure channel. DH is often used in conjunction with other algorithms, such as RSA, to provide secure communication.

- **ECC (Elliptic Curve Cryptography)**: ECC is a newer asymmetric encryption algorithm that is based on the properties of elliptic curves. ECC is considered to be more efficient than RSA and is becoming increasingly popular for applications that require high security and small key sizes.

- **DSA (Digital Signature Algorithm)**: DSA is a digital signature algorithm that is based on the discrete logarithm problem. DSA is used to verify the authenticity and integrity of digital documents.