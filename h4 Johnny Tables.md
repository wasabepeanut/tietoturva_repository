# x) OWASP 10 2021
## Broken Access Control

Description
- Attackers abuse misconfigured or the lack of security measures and human errors on a web or server, and attack with manual and/or automated attacks
- Some of the common vulnerabilities include the attacker gaining higher privileges with lower privilege user, bypassing the security checks by forcefully modifying some of the data and tampering with the metadata.

Prevention
- To prevent these attacks and to improve the security measures, common security measures that might seem obvious should not be ignored
- Logging the user logins, individually implementing permissions on specific operations and making sure confidential data is secured and not on public servers to minimize and possibly prevent these attacks.

## Security Misconfiguration

Description
- Improperly configured systems and networks expose the sensitive data and grant unauthorized access for attackers

Prevention
- Automation of some security processes and configurations, keeping the system and network minimalistic without unnecessary features and keeping the system up to date.

## Vulnerable and Outdated Components

Description
- Outdated softwares and components are vulnerable to exploits as attackers may abuse the known vulnerabilites of components.

Prevention
- Regular checks and updates on the software to keep the system up to date
- Scanning tools to check for vulnerabilities
- Removing unnecessary components and only using components from trusted sources

## Injection

Description
- The lack of validation and sanitization of untrusted data lead to data breaches and unauthorized actions
- Some common injection types include SQL, NoSQL and command injections

Prevention
- Implementing proper validation on specific data to allow only certain data formats
- Making use of security headers
- A last resort safety measure in case of an injection

# WebGoat
Following the instructions, we will proceed to install WebGoat to our Debian virtualbox.

First we are going to install Java for running Java archive files, with the following commands.

    sudo apt-get update
    sudo apt-get install openjdk-17-jre
![image](https://github.com/user-attachments/assets/e48ee87c-084c-422e-9029-fb84cc1797c1)

Since I have already installed firewall on my Debian, lets enable the firewall
![image](https://github.com/user-attachments/assets/58f7bbfe-1a92-409e-868a-3c2b094f91ad)

