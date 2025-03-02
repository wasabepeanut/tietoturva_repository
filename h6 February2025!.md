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


# m) John the Ripper
In this task our goal is to crack a ZIP archive password provided in the article.

## Installation
First we will need to install some tools and libraries:

    sudo apt-get update
    sudo apt-get -y install micro bash-completion git build-essential libssl-dev zlib1g zlib1g-dev zlib-gst libbz2-1.0 libbz2-dev atool zip wget

After executing the second command, I got an error in finding the package "zlib-gst".
After doing some searching in the web, I decided to execute the command again without this package.

## Compiling
After installing the tools and packages, we will then proceed to clone John (project) into our directory and do some configurations:

    git clone --depth=1 https://github.com/openwall/john.git
    cd john/src/	
    ./configure

After a while, the configure is ready and the command to compile is shown in the output:

    make -s clean && make -sj2

Now John is compiled. The new executables and scripts are located in the folder run/.

    cd ../run/
    ls -1

![image](https://github.com/user-attachments/assets/df380a27-19c8-409e-b9aa-e1aebf29d17b)

As we can see in the picture, the content matches the examples executables.

And at last we run John.

    $HOME/john/run/john

![image](https://github.com/user-attachments/assets/c1b025a9-7f74-48e3-9ae5-70da94b399e9)

## Cracking
By now we should have John the Ripper running.

We will now proceed to download Tero's ZIP file for cracking.

    wget https://TeroKarvinen.com/2023/crack-file-password-with-john/tero.zip

Now let us try to unzip the file to make sure it is password protected.

    unzip tero.zip

![image](https://github.com/user-attachments/assets/9453d64e-08f7-48bb-880d-a16fd019b36a)

As we can see the file is protected.

To crack a ZIP password we will have to complete a two step process: First extract the hash value into a new file.

    $HOME/john/run/zip2john tero.zip >tero.zip.hash

Second, perform a dictionary attack on the hash

    $HOME/john/run/john tero.zip.hash 

![image](https://github.com/user-attachments/assets/56786bea-ffea-4b31-969e-7c7a4055255c)

The attack was succesful, now we should be able get in the ZIP file with this password.

![image](https://github.com/user-attachments/assets/5f08db8c-46fc-4c3b-acf0-563765e54e46)

Now to show the content of the secret file.

    cat secretFiles/SECRET.md

![image](https://github.com/user-attachments/assets/e4981149-c983-4f66-9cd7-5ae8331d2cad)

We have now cracked our first file password. (Karvinen 9.2.2023)

# n) Crack a zip file password
After learning how to crack zip files let us crack our own zip file.

First we will create a txt file and zip the file with a password.

    nano gorillanote.txt
    zip -e secretstash.zip gorillanote.txt

After that we will run our previously learned commands to extract the hash.

    $HOME/john/run/zip2john secretstash.zip >secretstash.zip.hash

![image](https://github.com/user-attachments/assets/9c7b3c27-5389-4450-93f7-d56db4bd7405)

At last, execute the attack.

    $HOME/john/run/john secretstash.zip.hash

![image](https://github.com/user-attachments/assets/6b677ec0-9b9c-4a7a-b69d-a6ffd1c3d652)

The attack was succesful.

Let us see what is in the zip file.

    unzip secretstash.zip

![image](https://github.com/user-attachments/assets/54e89d78-a343-4159-8798-68393b17ff19)

![image](https://github.com/user-attachments/assets/dd13d91d-beac-47b0-b6c9-f1f16b503e8b)

The zip file contained a message.


# References
Karvinen, T. 9.2.2023. Crack File Password With John. Tero Karvinen. URL: https://terokarvinen.com/2023/crack-file-password-with-john/. Accessed: 3.3.2025.

Karvinen, T. 6.4.2022. Cracking Passwords with Hashcat. Tero Karvinen. URL: https://terokarvinen.com/2022/cracking-passwords-with-hashcat/. Accessed: 2.3.2025.

Schneier, B. 3.2015. Applied Cryptography: Protocols, Algorithms and Source Code in C, 20th Anniversary Edition. Chapter 2.3: One-Way Functions. O'reilly Media. URL: https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec003. Accessed: 2.3.2025.

Schneier, B. 3.2015. Applied Cryptography: Protocols, Algorithms and Source Code in C, 20th Anniversary Edition. Chapter 2.4: One-Way Hash Functions. O'reilly Media. URL: https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec004. Accessed: 2.3.2025.
