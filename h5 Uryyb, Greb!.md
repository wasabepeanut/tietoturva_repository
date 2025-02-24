# Applied Cryptography: Foundations
- In short, the article is about sending an encrypted message to a receiver. 
- The process of encryption in order:
  -> Plaintext: The message
  -> Encryption: Disguising the message
  -> Ciphertext: Encrypted message
  -> Decryption: Translating the ciphertext back to plaintext.
- Cryptography is often associated with authentication, integrity and nonrepudiation, on top of confidentiality.
 - Authentication: Message receiver should be able to locate the origin of the message.
 - Integrity: Receiver should be able to verify that the message has not been modified.
 - Nonrepudiation: Message sender should not be able to deny his sent message after the process
- Two general types of key-based algorithms:
  - Symmetric algorithm: encryption key can be calculated from the decryption key and vice versa. In most cases is based on a single key agreed beforehand by both parties (also known as single-key algorithm). 
  - Public-key algorithm: decryption and encryption keys are different from eachother. Encryption key often called public key and decryption private key. 
- Categories of breaking an algorithm (In decreasing order of severity):
  - Total break: the key is revealed to a cryptanalyst
  - Global deduction: a cryptanalyst finds a solution through an alternate algorithm
  - Instance deduction: a cryptanalyst finds the plaintext
  - Information deduction: a cryptanalyst gains some information about the key or plaintext. (Schneier, B. 2015)

# PGP
- 

# References
Karvinen, T. 17.11.2023. PGP - Send Encrypted and Signed Message - gpg. Tero Karvinen. URL: https://terokarvinen.com/2023/pgp-encrypt-sign-verify/. Accessed: 24.2.2025.

Schneier, Bruce. 3.2015. Foundations. O'reilly Media. URL: https://www.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/08_chap01.html#chap01-sec006. Accessed: 24.2.2025.
