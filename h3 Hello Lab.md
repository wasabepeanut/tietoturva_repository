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

- We succesfully learned how to find our network interfaces and turn them off.


# b) Portscan

# References
Bianchi, P. 5.8.2017. How to disable wireless from command line. Ask Ubuntu. URL: https://askubuntu.com/questions/597116/how-to-disable-wireless-from-command-line. Accessed 2.2.2025.

Karvinen, T. 3.2.2020. Command Line Basics Revisited. Tero Karvinen. URL: https://terokarvinen.com/2020/command-line-basics-revisited/. Accessed 2.2.2025.

Karvinen, T. 22.1.2021. Install Debian on Virtualbox - Updated 2024. Tero Karvinen. URL: https://terokarvinen.com/2021/install-debian-on-virtualbox/. Accessed 2.2.2025.

srivastavas260. 29.1.2024. Disabling and Enabling an Interface on Linux System. GeeksforGeeks. URL: https://www.geeksforgeeks.org/disabling-and-enabling-an-interface-on-linux-system/. Accessed 2.2.2025.

Vivek, G. 19.11.2024. Linux Show / Display Available Network Interfaces. Cyberciti. URL: https://www.cyberciti.biz/faq/linux-list-network-interfaces-names-command/. Accessed 2.2.2025.


