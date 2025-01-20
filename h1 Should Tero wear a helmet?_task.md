# x) Thread Modeling
## Threat modeling manifesto

Overall concept of threat modeling:
- Process of analyzing and identifying potential threats to a system
- Understanding the threats and creating countermeasures against them
- Making use of the key questions to help us evaluate the results of our threat modeling
- Everyone is able to and should threat model.

Why threat model?:
- Improves the security and privacy of the system
- Recognizing and pinpointing issues on the system early on
- Results of threat modeling might notify about new decisions to make in the system.

Benefits of Threat Modeling Manifesto:
- A guide to more effective and productive threat modeling
- Most effective during early phase of analysis
- Following the patterns and avoiding anti-patterns ensures efficient threat modeling
- Not a direct solution to elimination threats, but a useful guide.

https://www.threatmodelingmanifesto.org/


## Welcome to the Worlds Shortest Threat Modeling Course

Overall concept of threat modeling:
- Set of methods designed to guide the planning and building of a highly secure system
- Revolves around answering the four key questions:
  1. What are we working on?
     - Visualize our thoughts and collaborate with others (Data Flow charts)
     - Record our work to documents, which might lead to some details of our work.
       
  2. What can go wrong?
     - STRIDE, making sure that we have one of each threat type in STRIDE might result in better answers and threat modeling
     - Kill chain
     - Paying attention to answers.
       
  3. What are we going to do about it?
     - Tracking our progress and making use of every single threat in our development
     - Risk management, assessing the threat to help us make a decision.
    
  5. Did we do a good enough job?
     - "Would you recommend threat modeling?", which answers to the question.

Why threat model?:
- To anticipate threats in the early phase, reducing the costs and resources to eliminate them

https://www.youtube.com/playlist?list=PLCVhBqLDKoOOZqKt74QI4pbDUnXSQo0nf


## Threat Modeling Cheat Sheet

Overall concept of threat modeling:
- Structured and repeatable process to gain insights into the security details of a system
- Analyzing system from the attacker's "point of view", focusing on the ways the attacker can exploit a system.
- Should be kept up to date and maintained beside the system
- Should be treated as an essential task in the process

Why threat model?:
- Important concept to keep in mind
- Helps to identify threats and regulate responses to them
- Securing the system right from the start, to avoid subsequent problems
- Heightens the participants mindset through feedbacks and team effort

Challenges of threat modeling:
- Overlooking potential threats or incorrectly assessing risks due to lack of experience and/or knowledge
- Time-consuming, which may lead to tight schedules and pressure to succeed
- Communication between different parties, which might misdirect the threat model or result in an incomplete threat model

https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html


# x) Infosec scene: EP 45: XBox Underground (Part 1)
- A teenage hacker group XBox Underground
- responsible for unprecedented cyber attacks on some of the biggest tech firms in the world
- Members:
  - David Pokora (Xenomega)
  - Sanad Nesheiwat (Sonic)
  - Nathan Leroux (animefre4k)
  - Austin Alcala (AAmonkey)
  - Dylan Wheeler (SuperDaE)
  - Justin May (MTW)

- With the release of their new console Xbox 360 in 2005, Microsoft upgraded their security to avoid development kits (DevKit) getting in the hands of unwanted individuals
- Eventually some DevKits end up online and for sale on online stores
- In 2008 David manages to gain several DevKits which grant him access to Xbox developers' testing environment
- David gains popularity by leaking unreleased information from the environment
- Other hackers start to get interested and want to participate in the hacking activities
- In 2011 Dylan gets a list of Epic Games accounts and finds an IT employee' credentials in it
- Credentials grant the hackers access to Epic Games' servers and their first big discovery, an unreleased game called "Gears of War 3"
- Epic Games contacts the FBI because the game is leaked online, but with no leads yet
- Dylan finds another file containing all the company's employees' credentials, granting him full access to the network
- Through going through files, Dylan makes a great discovery and manages to further hack into some major companies networks' (such as Activision, Microsoft, Valve, EA, Bungie, Blizzard Entertainment)
- Group expands their hacking and hack into several major companies which stray further from gaming (which was the main objective at the start)
- Through Zombie studios, they discover a secret path to U.S military server, where they are working on an Apache Simulator game
- Over the 2 years the group has been doing activities that could lead them to prison, which they are aware of and jokingly talk what they would call their gang in prison, Underground Xbox.

https://darknetdiaries.com/episode/45/
https://www.youtube.com/watch?v=LZkl0_9xFOU


# a) Security hygiene
While the security practices that a person or a company might need depends on the situation, there are some common practices that are recommended to follow which also occur in our everyday life.
These are for example:
- Strong and unique passwords
- Multi-Factor Authentication
- Software/device updates
- Antivirus software
- Securing your devices
- Backing up data
- Being wary of scams


# b) Make-belief boogie-man
This threat model is for a imaginary health care clinic

## 1. What are we working on?
Key assets:
- Customer health data
- Customer billing and personal information data
- Software and firmware

Security Supports Business:
- For the health care clinic, customer trust is essential. Company relies heavily on customer confidentiality and without it the company's economy and reputation would crash
- Managing inventory and making sure the company has everything available (such as devices)

Customer Touchpoints:
- Website, where customers can ask for assistance, manage account settings and see information on the company
- Cloud, where we store the customers data for analyzing and storing.

## What can go wrong?
STRIDE MODEL:
- Spoofing: Attacker steals customer credentials by impersonating the company
- Tampering: Attacker tampers with the customer data
- Repudiation: Attacker modifies the logs to spread false information
- Information Disclosure: Attacker gains access to customer data through cloud breach
- Denial of Service (DoS): Attacker disrupts the website or cloud, making them unaccessible to both employees and customers
- Elevation of Privilige: A user might get access to admin rights to the servers

Prioritization of Risks:
- High: Health data breach
- Medium: Tampering
- Low: DoS

## What are we going to do about it?
Minimize Exposure
- Multi-factor authentication
- Securing the website and database

Limiting access
- Restricting access to database from unauthorized personnel
- Proper validation to make sure data is correct

## Did we do a good enough job?
- Customer satisfaction and company reputation
- Low count of data breaches and incidents

