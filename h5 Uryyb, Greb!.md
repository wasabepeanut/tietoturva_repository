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
- # Applied Cryptography: Foundations
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
  - Information deduction: a cryptanalyst gains some information about the key or plaintext. (Schneier 3.2015)

# PGP
- GNU privacy guard, or "gpg" is a popular tool used for PGP encryption.
- Public and secret key generated
![image](https://github.com/user-attachments/assets/62e128e6-06ff-47a3-bea7-f261d2de7e0e)

- public key export
![image](https://github.com/user-attachments/assets/a0775013-9b56-4a3c-8366-50abf0393cb6)

- alice gpg homedir
![image](https://github.com/user-attachments/assets/bb7dd3d7-31e2-4a5e-9d20-164428f71d00)

- alice keys
![image](https://github.com/user-attachments/assets/12862c98-f7c4-4232-9b36-66aa832a99b1)

- importing key to alice
![image](https://github.com/user-attachments/assets/beb06955-e6ae-4285-ac53-fc19ac2b3665)

- Alice signed my key
![image](https://github.com/user-attachments/assets/bc3f5d2f-f6e2-40e2-9e04-87c6412259a3)

- I sign alice' key
![image](https://github.com/user-attachments/assets/aea037a6-becd-49c3-b2ea-de916ee49afa)

asda

# References
Karvinen, T. 17.11.2023. PGP - Send Encrypted and Signed Message - gpg. Tero Karvinen. URL: https://terokarvinen.com/2023/pgp-encrypt-sign-verify/. Accessed: 24.2.2025.

Schneier, Bruce. 3.2015. Foundations. O'reilly Media. URL: https://www.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/08_chap01.html#chap01-sec006. Accessed: 24.2.2025.

# References
Karvinen, T. 17.11.2023. PGP - Send Encrypted and Signed Message - gpg. Tero Karvinen. URL: https://terokarvinen.com/2023/pgp-encrypt-sign-verify/. Accessed: 24.2.2025.

Schneier, Bruce. 3.2015. Foundations. O'reilly Media. URL: https://www.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/08_chap01.html#chap01-sec006. Accessed: 24.2.2025.
