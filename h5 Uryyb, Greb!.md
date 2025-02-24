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
  - Information deduction: a cryptanalyst gains some information about the key or plaintext. (Schneier 3.2015)


# PGP
- GNU privacy guard, or "gpg" is a popular tool used for PGP encryption.
- In the article we will be taught hands on experience on how to generate the keys, encrypt and decrypt a message between two parties.
- We can verify the other' public keys after checking them and marking them as trusted. This will allow the sender to verify the correct receiver and the receiver to verify the origin of the message.

## Encryption and decryption practice

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

Alice wants to sign the messages she sends to me, so we will have to do the same process for myself.

After the process I have Alice' public key and marked it as trusted.

Now Alice sends me a message and encrypts it.

    cd alice
    micro message.txt

    gpg --homedir . --encrypt --recipient tero@example.com.invalid --sign --output     encrypted.pgp --armor message.txt

After this Alice has generated the message in an encrypted file called "encrypted.pgp", and sends it to me.

    cd
    cp -v alice/encrypted.pgp

I have received a new encrypted message, let us decrypt it 

    gpg --decrypt encrypted.pgp

![image](https://github.com/user-attachments/assets/41a413ae-6e6b-4fae-ac24-afa70e6e2d66)

Aftermath: I have now learned how to generate keypairs and send encrypted messages with the gpg tool. This was my first time doing this so it was interesting and nice to learn something new. 


# OpenSSH
## Installation
First let us install openSSH server

    sudo apt install openssh-server

After installing the ssh server, let us connect to it using our own username and ip address.

    ssh duyp@localhost
![image](https://github.com/user-attachments/assets/5c4d5e70-f8dc-4c01-ae0f-da4b6b319e72)

As we can see with the "who" command, there are 2 users now logged in the server, which means that we have succesfully connected to our ssh.
![image](https://github.com/user-attachments/assets/7921133b-4587-471a-af46-bf7a72a16689)

## Automation

We will now proceed to automate the earlier process using keypairs. First we will generate the keys.

    ssh-keygen
![image](https://github.com/user-attachments/assets/62051f06-3e48-48e0-a91e-14c4f307e9b1)

After generating the ssh-key, let us copy this key to the ssh server.

    ssh-copy-id duyp@localhost
![image](https://github.com/user-attachments/assets/60398a80-95ff-4df6-a153-eaf0c758529a)

Now we are able to login to our ssh server without password.

# Password manager
For this task I chose "Pass" as my cloudless and open password manager.

Reasons to use password manager:
- Strong and unique passwords for every platform, to avoid reusing passwords
- Protection against phishing attacks
- Time efficiency
- Multi-factor Authentication


# References
Karvinen, T. 17.11.2023. PGP - Send Encrypted and Signed Message - gpg. Tero Karvinen. URL: https://terokarvinen.com/2023/pgp-encrypt-sign-verify/. Accessed: 24.2.2025.

Schneier, Bruce. 3.2015. Foundations. O'reilly Media. URL: https://www.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/08_chap01.html#chap01-sec006. Accessed: 24.2.2025.

