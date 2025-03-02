# One-Way Functions
- A core element of public-key cryptography. 
- Are difficult to reverse, compared to how they are determined.
- Example from the book shortened: It is easy to break a plate, but not as easy to put the broken    pieces together.
- Technically, one-way functions might not be real, but many functions seem that way. E.g. Fixing
  a broken plate might not be impossible, but is really difficult.
- Trapdoor one-way function: one-way function that makes the difficult part achievable with       secret information. (Schneier 3.2015)

# One-Way Hash Functions
- A core element in modern cryptography.
- In short, converts a input string (**pre-image**) into an fixed-length output string (**hash    value**).
- Collision-free: Two  pre-images can not be determined with the same hash value.
- Message authentication code (MAC): One-way function with a secret key. Hash value can be     
  verified only by one with the key. (Schneier 3.2015)

# a) Hashcat 🐈
- Tool to "crack" hash values by going through every word in the dictionary.

## Installation
In this task we will install Hashcat to crack the hash value in our upcoming task b).

First we will proceed to install the app in our virtualbox.

    sudo apt-get update
    sudo apt-get -y install hashid hashcat wget

After installing hashcat, we will create a new directory.

    mkdir hashed
    cd hashed

Then we will need a dictionary, which we will get with the commands:

    wget https://github.com/danielmiessler/SecLists/raw/master/Passwords/Leaked-      Databases/rockyou.txt.tar.gz

![image](https://github.com/user-attachments/assets/07735681-fbfc-438b-b22f-38fab33ba01f)
    
    tar xf rockyou.txt.tar.gz
    rm rockyou.txt.tar.gz

Now that we have our dictionary, let us try wordcount command to check our dictionary.

    wc -l rockyou.txt

![image](https://github.com/user-attachments/assets/7757ddff-32b4-48f3-a624-764dfc3d9b33)

## Cracking
After the installation process, we can proceed to do our first cracking.
First we will need to determine the right type of the hash with the command:

    hashid -m [hash]

![image](https://github.com/user-attachments/assets/10a1f39b-0f19-4ecf-affa-384f099c50fc)

According to the instructions, the right type is typically one of the top 3, and the most common out of those three is MD5, so we will proceed with MD5.

    hashcat -m 0 '[hash]' rockyou.txt -o solved

![image](https://github.com/user-attachments/assets/73140922-5c74-439e-9e48-2ed310eeeea8)

After a while we get our results. Status: Cracked means that we have succesfully cracked the hash, which will be located in a file "solved" created to our working directory.

Let us see what was the hash:

    cat solved

![image](https://github.com/user-attachments/assets/bd72a46a-b045-476d-b99c-b0f0f4e10e60)

As we can see the hash equals to summer. (Karvinen 6.4.2022)

# b) Crack the hash
In this task we will use our previously learned skills to crack the hash provided by our lecturer.

First I will try to determine the type of the hash with the command:

    hashid -m d595b2086532422bbe654bc07ea030df

![image](https://github.com/user-attachments/assets/f8ecc2fa-e3ee-43c2-b342-db731338bb79)

Since this hash had the same types as top 3, I will do the same procedures and try MD5.

    hashcat -m 0 'd595b2086532422bbe654bc07ea030df' rockyou.txt -o solved

After waiting for a while, our hash got cracked:

![image](https://github.com/user-attachments/assets/30db0453-1acd-4f4f-a0d9-2067af4c58c7)

# References
Karvinen, T. 6.4.2022. Cracking Passwords with Hashcat. Tero Karvinen. URL: https://terokarvinen.com/2022/cracking-passwords-with-hashcat/. Accessed: 2.3.2025.

Schneier, B. 3.2015. Applied Cryptography: Protocols, Algorithms and Source Code in C, 20th Anniversary Edition. Chapter 2.3: One-Way Functions. O'reilly Media. URL: https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec003. Accessed: 2.3.2025.

Schneier, B. 3.2015. Applied Cryptography: Protocols, Algorithms and Source Code in C, 20th Anniversary Edition. Chapter 2.4: One-Way Hash Functions. O'reilly Media. URL: https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec004. Accessed: 2.3.2025.
