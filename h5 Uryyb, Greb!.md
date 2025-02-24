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
- In this exercise we are simulating a "real conversation" between me and Alice, using gpg.
  
First we shall update our machine and install the tools with the commands:

    sudo apt-get update
    sudo apt-get install gpg micro psmisc

After installing the tool, I generated my keypair.

    gpg --gen-key
![image](https://github.com/user-attachments/assets/62e128e6-06ff-47a3-bea7-f261d2de7e0e)

Since Alice is not actually real, we will simulate an Alice and give her own settings.

    mkdir alice/
    chmod og-rwx alice/
    cd alice
    gpg --homedir . --fingerprint
![image](https://github.com/user-attachments/assets/bb7dd3d7-31e2-4a5e-9d20-164428f71d00)

Now let us generate Alice her own keys

    gpg --homedir . --gen-key
![image](https://github.com/user-attachments/assets/12862c98-f7c4-4232-9b36-66aa832a99b1)

Now if Alice wants to communicate with me, she will need my public key, which I will first need to export and send it to her (because Alice is not real).

    gpg --export --armor --output duy.pub
    cp -v duy.pub alice/
    
After receiving the export, Alice will have to import the key for it to be usable.

    gpg --homedir . --import duy.pub
    gpg --homedir . --fingerprint

![image](https://github.com/user-attachments/assets/a0b73497-32d2-46d0-8e44-979ed32ac8de)

Now that Alice has my public key, Alice will sign it to mark it as trusted.

    gpg --homedir . --sign-key "3F04 4F7C 7846 FC60 78E9 53A9 98F9 9AEF 82D4 65AD"

![image](https://github.com/user-attachments/assets/bc3f5d2f-f6e2-40e2-9e04-87c6412259a3)

- I sign alice' key

![image](https://github.com/user-attachments/assets/aea037a6-becd-49c3-b2ea-de916ee49afa)

- Decrypting the message

![image](https://github.com/user-attachments/assets/41a413ae-6e6b-4fae-ac24-afa70e6e2d66)


# References
Karvinen, T. 17.11.2023. PGP - Send Encrypted and Signed Message - gpg. Tero Karvinen. URL: https://terokarvinen.com/2023/pgp-encrypt-sign-verify/. Accessed: 24.2.2025.

Schneier, Bruce. 3.2015. Foundations. O'reilly Media. URL: https://www.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/08_chap01.html#chap01-sec006. Accessed: 24.2.2025.

# References
Karvinen, T. 17.11.2023. PGP - Send Encrypted and Signed Message - gpg. Tero Karvinen. URL: https://terokarvinen.com/2023/pgp-encrypt-sign-verify/. Accessed: 24.2.2025.

Schneier, Bruce. 3.2015. Foundations. O'reilly Media. URL: https://www.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/08_chap01.html#chap01-sec006. Accessed: 24.2.2025.
