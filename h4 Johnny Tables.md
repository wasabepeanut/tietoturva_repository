# x) OWASP 10 2021
## Broken Access Control

Description
- Attackers abuse misconfigured or the lack of security measures and human errors on a web or server, and attack with manual and/or automated attacks
- Some of the common vulnerabilities include the attacker gaining higher privileges with lower privilege user, bypassing the security checks by forcefully modifying some of the data and tampering with the metadata.

Prevention
- To prevent these attacks and to improve the security measures, common security measures that might seem obvious should not be ignored
- Logging the user logins, individually implementing permissions on specific operations and making sure confidential data is secured and not on public servers to minimize and possibly prevent these attacks. (OWASP)

## Security Misconfiguration

Description
- Improperly configured systems and networks expose the sensitive data and grant unauthorized access for attackers

Prevention
- Automation of some security processes and configurations, keeping the system and network minimalistic without unnecessary features and keeping the system up to date. (OWASP)

## Vulnerable and Outdated Components

Description
- Outdated softwares and components are vulnerable to exploits as attackers may abuse the known vulnerabilites of components.

Prevention
- Regular checks and updates on the software to keep the system up to date
- Scanning tools to check for vulnerabilities
- Removing unnecessary components and only using components from trusted sources. (OWASP)

## Injection

Description
- The lack of validation and sanitization of untrusted data lead to data breaches and unauthorized actions
- Some common injection types include SQL, NoSQL and command injections

Prevention
- Implementing proper validation on specific data to allow only certain data formats
- Making use of security headers
- A last resort safety measure in case of an injection. (OWASP)

# a) Installing WebGoat
Following the instructions, we will proceed to install WebGoat to our Debian virtualbox.

First we are going to install Java for running Java archive files, with the following commands.

    sudo apt-get update
    sudo apt-get install openjdk-17-jre
![image](https://github.com/user-attachments/assets/e48ee87c-084c-422e-9029-fb84cc1797c1)

Since I have already installed firewall on my Debian, lets enable the firewall

    sudo ufw enable
![image](https://github.com/user-attachments/assets/58f7bbfe-1a92-409e-868a-3c2b094f91ad)

After rebooting our virtualbox, we can now proceed to install WebGoat and run it according to the instructions.

    java -Dfile.encoding=UTF-8 -Dwebgoat.port=8888 -Dwebwolf.port=9090 -jar webgoat-2023.8.jar
![image](https://github.com/user-attachments/assets/8ffa9c80-6497-41c3-9bef-c56ba4640936)

After creating my user, I have succesfully logged in WebGoat.

# b) WebGoat, Developer tools

After logging in WebGoat, we will proceed to our first task, Developer Tools.

Let us test our console in the WebGoat to check if it works correctly.
![image](https://github.com/user-attachments/assets/9e84e056-ec7c-4bc3-a147-67d24dc7a803)

Now for our first actual task in Developer Tools we should get a response from the console and copypaste the random number to the textfield

    webgoat.customjs.phoneHome()
![image](https://github.com/user-attachments/assets/41efa005-c256-4a29-8d3c-5e18d83b9b20)

![image](https://github.com/user-attachments/assets/9b2b3186-d0ce-4497-ad7a-155468d273f2)

The randomly generated number was correct.

In the second task we will click a button to make a HTTP request, after which we will have to find a specific request with a content networkNum.

![image](https://github.com/user-attachments/assets/069c1253-1bff-45be-bb0a-724301b03340)

![image](https://github.com/user-attachments/assets/64c46075-d3bd-4b2c-a341-8fde7cf81d0b)

Our second task is now done. (Karvinen 13.11.2023)

# c) Updating Linux
On this task we will update our operating system and every application on our Linux

Let us commit these next commands
    
    sudo apt-get update
    sudo apt-get dist-upgrade

After a few seconds the update is complete.

# d) SQLZoo
On this task we will proceed to SQLZoo and complete the tasks "0 SELECT basics"and "2 SELECT from World".

## 0 SELECT 
Task 1:

    SELECT population FROM world
      WHERE name = 'Germany'

![image](https://github.com/user-attachments/assets/6eb87c1d-1614-4d5b-87a9-b8ee28bf8504)

Task 2:

    SELECT name, population FROM world
      WHERE name IN ('Sweden', 'Norway', 'Denmark');

![image](https://github.com/user-attachments/assets/4959facb-d2e7-49c9-b38d-4302feba3ef4)

Task 3:

    SELECT name, area FROM world
      WHERE area BETWEEN 200000 AND 250000
    
![image](https://github.com/user-attachments/assets/1b468f00-655a-432a-9b5a-fd1e074b7fc3)

## 2 SELECT
Task 1:

    SELECT name, continent, population FROM world

![image](https://github.com/user-attachments/assets/588b38d7-b9ca-4363-b670-f61d08cdd983)

Task 2:

    SELECT name FROM world
    WHERE population > 200000000    

![image](https://github.com/user-attachments/assets/1112f427-bc2b-4f36-8bfd-4aa033bd2336)

Task 3:

    SELECT name, gdp/population FROM world
    WHERE population > 200000000

![image](https://github.com/user-attachments/assets/3a43104e-8ecd-489f-9f71-dc8323a64713)

Task 4:

    SELECT name, population/1000000 FROM world
    WHERE continent = "South America"

![image](https://github.com/user-attachments/assets/5be5e6d9-d35e-428f-9a4f-a417bec427ca)

Task 5:

    SELECT name, population FROM world
    WHERE name in ('France', 'Germany', 'Italy')

![image](https://github.com/user-attachments/assets/5352ab1e-b6fe-41d5-a54a-c7e4173fe753)

Task 6:

    SELECT name FROM world
    WHERE name LIKE "%United%"

![image](https://github.com/user-attachments/assets/e0230941-d45a-42ca-a0ea-53961d946898)

Task 7:

    SELECT name, population, area FROM world
    WHERE area > 3000000 OR population > 250000000

![image](https://github.com/user-attachments/assets/caf163ec-3a35-440b-87f6-55a2d7e500e0)

Task 8:

    SELECT name, population, area FROM world
    WHERE (area > 3000000 AND population < 250000000) 
    OR 
    (area < 3000000 AND population > 250000000)

![image](https://github.com/user-attachments/assets/89835946-4bbf-42c8-9a3e-479a8dca9bfd)

Task 9:

    SELECT name, ROUND(population/1000000, 2), ROUND(gdp/1000000000, 2) FROM world
    WHERE continent = 'South America'

![image](https://github.com/user-attachments/assets/46c4a62b-5960-4006-a502-e6a69beb6b0d)

Task 10:

    SELECT name, ROUND(gdp/population, -3) FROM world
    WHERE gdp >= 1000000000000

![image](https://github.com/user-attachments/assets/0586223c-1b21-4541-a02a-79d5689270d3)

Task 11:

    SELECT name, capital FROM world
     WHERE LENGTH(name) = LENGTH(capital)

![image](https://github.com/user-attachments/assets/e57b6c24-6fb2-4960-b5c5-79f90c55f555)

Task 12:

    SELECT name, capital FROM world
    WHERE LEFT(name, 1) = LEFT(capital, 1)
    AND
    name != capital

![image](https://github.com/user-attachments/assets/cfc948b6-d55b-408c-bfdb-e55d8e4c44ab)

Task 13:

    SELECT name FROM world
    WHERE name LIKE '%a%'
      AND name LIKE '%e%' 
      AND name LIKE '%i%' 
      AND name LIKE '%o%' 
      AND name LIKE '%u%'
      AND name NOT LIKE '% %';

![image](https://github.com/user-attachments/assets/41f6d4ee-7f5e-4d67-b55f-e07d77cb19d5)

# References

OWASP. A01:2021 – Broken Access Control. OWASP Top 10 - 2021. URL: https://owasp.org/Top10/A01_2021-Broken_Access_Control/. Accessed 10.2.2025.

OWASP. A03:2021 – Injection. OWASP Top 10 - 2021. URL: https://owasp.org/Top10/A03_2021-Injection/. Accessed 10.2.2025.

OWASP. A05:2021 – Security Misconfiguration. OWASP Top 10 - 2021. URL: https://owasp.org/Top10/A05_2021-Security_Misconfiguration/. Accessed 10.2.2025.

OWASP. A06:2021 – Vulnerable and Outdated Components. OWASP Top 10 - 2021. URL: https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/. Accessed 10.2.2025.

Karvinen, T. 13.11.2023. Try Web Hacking on New Webgoat 2023.4. Tero Karvinen. URL: https://terokarvinen.com/2023/webgoat-2023-4-ethical-web-hacking/. Accessed 10.2.2025.
