# Installing Debian and Command Lines Basics
- By following the instructions, I succesfully downloaded and learned how to download Debian on my virtual machine
- I also succeeded in installing the optional features following the same instructions. (Karvinen 22.1.2021)

- Basic commands that everyone should know and are useful for navigating and operating in the Linux command line (CMD):
    - pwd = tells you the current directory you are working in
    - ls = lists the content
    - cd = changing directiories
    - mv = moving and renaming files/directories
    - cp = copy a file/directory
    - rm = remove a file/directory
- It is possible to get the description and help on a command by typing "man" and the command you want help with
- By applying "sudo" at the start of a command, you gain "high privilege" which allows you to make operations requiring admin rights
- It is important to get the latest available features on your system, by giving the command "sudo apt-get update", which updates the system by installing the latest available packages. (Karvinen 3.2.2020)

# a) Can't fish
- At the start of this task, I tried pinging the servers to first check that everything works normally
- After checking that everything is okay, I listed all my network interfaces with the command "ip a" or "ip link show" (Vivek 19.11.2024).

![image](https://github.com/user-attachments/assets/b8951ee4-54d6-4554-a36e-966d99c4ad38)
- As we can see from the screenshot, we have 2 interfaces named "lo" and "enp0s3".

- Turning off the networking with the command "sudo ip link [Interface name] down" (srivastavas260. 29.1.2024).

![image](https://github.com/user-attachments/assets/a5a57d4a-d705-46fc-a98f-9c40e4366747)

- An alternative way to shutdown all the interfaces, is by giving the command "nmcli networking off" (Bianchi 5.8.2017).

![image](https://github.com/user-attachments/assets/726337f9-ec2f-4c74-8375-c8e8908cd2c1)

- We have now shut down both interfaces and shouldn't be able to ping now.

![image](https://github.com/user-attachments/assets/20e35da3-2e25-48b4-9ea3-a1923da70ff0)

- As we can see "Network is unreachable" indicates that pinging is now not possible.

- We succesfully learned how to find our network interfaces and turn them off.


# b) Portscan
- At the start of this task, we will first need to install nmap tool for portscan (James 30.6.2024).

![image](https://github.com/user-attachments/assets/1e415e94-9c52-499f-8763-0a3b20d81087)

- Afterwards we can now turn off the networking for safety measures.

![image](https://github.com/user-attachments/assets/3e9e1cc8-52c3-4174-8c4f-40ed397caf33)

- After checking that networking is turned off, we can start a basic portscan with a command "sudo nmap -A localhost".

![image](https://github.com/user-attachments/assets/0742f332-f8b5-41db-a175-d9d4df35a969)

- From the report we can see the details of the portscan which provides us with different information.
- Ex:

  - Date of the scan:
  
  ![image](https://github.com/user-attachments/assets/6f3f24ba-55c2-44a2-abc9-79aaef692117)

  - Target of the scan:
  
  ![image](https://github.com/user-attachments/assets/22e533f9-02ee-4d7f-bed0-d0b2666a4c20)

  - Ports and information regarding them:

  ![image](https://github.com/user-attachments/assets/1daa75fa-b61e-4cf9-8e04-93e6f0dfc161)

- We have now succesfully learned how to perform portscans for localhost.

# c) Daemon scan

- For this task we will first enable networking again and then install a Daemon server (Karvinen 2025).

![image](https://github.com/user-attachments/assets/95e41bd3-ddf1-4c7f-8e10-0d34c91f41d1)

- After succesfully installing the Daemon, we can now proceed to disable the networking again and proceed to portscan.

![image](https://github.com/user-attachments/assets/7ad9dfc7-a49d-462a-9f2c-01687ee7e759)

- From the report we can now see that we have installed 2 new ports to our interface, ports 80/tcp and 631/tcp.

# d) OverTheWire
## Level 0
- At the start of this task we will first install ssh to our virtual machine.

- Afterwards we will proceed to login to our game with the command "ssh [user]@[host]" with the information provided on the website.
- Since the port number was also provided on the website, we can add a parameter "-p" to indicate our port.

![image](https://github.com/user-attachments/assets/8a8f544c-eb47-4ee8-8fd0-015558ab0f9d)
![image](https://github.com/user-attachments/assets/92eee7f0-8b66-48ae-94e8-296b874e60a2)

- After typing in the password, we are now in the game.

## Level 1
- At first we can already see that we are in the home directory by the ~ sign.
- As the task already gave us the name of the file, we can proceed to print the file "readme"

![image](https://github.com/user-attachments/assets/78608642-42c3-45f0-afd4-89ec8ebc87d8)

- With the password we can now proceed to login to the next user and go to the next level

## Level 2
- There is a file named "-" which causes problems when using with commands like cat.
- Therefore we will need to add a prefix with the command "./-", now we the command should understand that we mean the dash as a text and not as an operator. (Linux.die.net)

![image](https://github.com/user-attachments/assets/7025ef49-1a0b-4eed-ae8b-6011c20efda7)

- We can now proceed to level 3

## Level 3
- In this stage we have a file containing spaces in its name.
- 2 options to escape this; wrapping the name in quotes ("") or adding backslash (\) for every space (Prakash 23.11.2023).
- You can also easily bypass these two if it is possible to identify the file uniquely and pressing tab, which does all the work for you.

![image](https://github.com/user-attachments/assets/0aa573fd-6e05-4a9d-b4a5-d9bd692e3ebf)

- Now we can proceed to level 4

## Level 4
- In this stage we have a directory named "inhere" which contains a hidden file with the password
- First let us move to the directory and then list all the files, including the hidden ones with a parameter -a.

![image](https://github.com/user-attachments/assets/96935b1a-59eb-462d-8259-f0dd8a56f666)

- We can now see 3 hidden files with one named "...Hiding-From-You"
- Let's use "cat" command to print the content of the file

![image](https://github.com/user-attachments/assets/b9d3f646-db94-48d4-bb34-d6a947239d94)

- We have now succesfully completed the last mandatory task.


# References
Prakash, A. 23.11.2023. How to Tackle Filenames With Spaces in Linux. Linux Handbook. URL: https://linuxhandbook.com/filename-spaces-linux/. Accessed 3.2.2025.

Bianchi, P. 5.8.2017. How to disable wireless from command line. Ask Ubuntu. URL: https://askubuntu.com/questions/597116/how-to-disable-wireless-from-command-line. Accessed 2.2.2025.

James, J. 30.6.2024. How to Install Nmap on Debian 12, 11 or 10. LinuxCapable. URL: https://linuxcapable.com/how-to-install-nmap-on-debian-linux/. Accessed. 3.2.2025.

Karvinen, T. 3.2.2020. Command Line Basics Revisited. Tero Karvinen. URL: https://terokarvinen.com/2020/command-line-basics-revisited/. Accessed 2.2.2025.

Karvinen, T. 22.1.2021. Install Debian on Virtualbox - Updated 2024. Tero Karvinen. URL: https://terokarvinen.com/2021/install-debian-on-virtualbox/. Accessed 2.2.2025.

Karvinen, T. 10.1.2025. Information Security. Tero Karvinen. URL: https://terokarvinen.com/information-security/. Accessed 3.2.2025.

Linux.die.net. Advanced Bash-Scripting Guide. URL: https://linux.die.net/abs-guide/special-chars.html. Accessed 3.2.2025.

srivastavas260. 29.1.2024. Disabling and Enabling an Interface on Linux System. GeeksforGeeks. URL: https://www.geeksforgeeks.org/disabling-and-enabling-an-interface-on-linux-system/. Accessed 2.2.2025.

Vivek, G. 19.11.2024. Linux Show / Display Available Network Interfaces. Cyberciti. URL: https://www.cyberciti.biz/faq/linux-list-network-interfaces-names-command/. Accessed 2.2.2025.


