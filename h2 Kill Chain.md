# x) Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains
## 1 Introduction
- A new group of threats known as "Advanced Persistent Threat" (APT) are exploiting the common security measures to attack the systems
- The new threats are using advanced technology build to defeat the most common defense mechanisms
- To defend against these threats, it is necessary to build a defense based on the threats and attack patterns
- Mapping each attack to their own category and choosing the right defense method against them is the key to reducing and eliminating the threats

- Most organizations rely on solutions that reduce risks related to automated threats, which might not be the best defense against manually operated attacks
- Common incident response methods fail because of two inaccurate assumptions:
  - They react only after the attacks has gone through, which in some cases might be too late
  - They assume that the attack relies only on specific vulnerabilites and ignore the adaptive and cunning methods of an attack
- Responding to APT attacks required more advanced and intelligent solutions, thus introducing "kill chain" an approach to threats from the attackers perspective where each individual phase of an attack was mapped to their own category
- Following the guide, the defenders could acquire an advantage over the attacks by anticipating the next moves and preparing a defense.
  
## 2 Related Work
- Attack-Based Sequential Analysis of Countermeasures (ABSAC)
  - Approach that offers solutions based on the countermeasures rather than the early detection of an attack
- Situational Crime Prevention (SCP)
  - Approach models crime from the offender' perspective and maps the phases of a crime
 
## 3 Intelligence-driven Computer Network Defense
- A strategy that responds to threats, and analyses their capabilities, objectives and limitations
- Treats the intrusions as phased progressions using a kill chain model to analyze the intrusions and preparing defenses against them
- The strategy yields a more secure defense measures by mapping each intrusion to their own phase. In the kill chain breaking even one phase of the intrusion terminates the threat

### 3.1 Indicators and the Indicator Life Cycle
- Indicator = Any information that objectively describes an intrusion
- Can be divided to three types:
  - Atomic = Cannot be broken into smaller parts and retain their meaning within the context of an intrusion (ex. email address, IP address)
  - Computed = Derived from date involved in an incident (ex. regex, hash values)
  - Behavioral = Group of computed and atomic indicators, often subject to qualification by quantity and possibly combinatorial logic

- Indicator life cycle involves the identification, maturation and utilization of indicators through collaboration and analysis
- Applies to all indicators indiscriminately, regardless of their relevance or accuracy
- Tracking efficiently prevents future problems and applying wrong techniques to threats
- Properly validating and analyzing the indicators secures an effective and trustworthy process

### 3.2 Intrusion Kill Chain
- A systematic process to mitigate threats and achieve the desired results
- Consists of 7 phases:
  - Reconnaissance: Research, identification and selection of targets
  - Weaponization: Coupling exploit into a deliverable payload
  - Delivery: Transmission of the weapon to the targeted environment
  - Exploitation: After transmission, triggers a code for the intruder to exploit a specific target, such as application
  - Installation: Installing malware on the system
  - Command and Control (C2): Intruders gains access to manually operate in the target environment
  - Actions on Objectives: After succesfully completing the earlier tasks, taking action on the original objective of this attack (for ex. data exfiltration, sabotage)

### 3.3 Courses of Action
- Using the kill chain to match the security capabilities with the corresponding phase can help measure the performance and effectiveness of each capability, and also plan the future investments
- Essential part of intelligence-driven CND where security decisions are based on a deep understanding of the adversary
- Furthermore the security measures can be mapped to their own categories using a course of action matrix describing each actions purpose
- A course of action matrix based on DoD information operations consists of detect, deny, disrupt, degrade, deceive and destroy

### 3.4 Intrusion Reconstruction
- Kill chain analysis assists analysts in understanding the available information and defensive actions for each intrusion at a specific phase
- Analysts must discover more attributes of the threat to find more solutions
- Previous phases of an threat can be assumed as successful and require full analysis for an effective mitigation
- Fully understanding and eliminating intrusions can force the adversaries to change their intrusion methods
- Quickly responding to intrusions with countermeasures reduces the probabilities of an intrusion

### 3.5 Campaign Analysis
- Strategically analyzing multiple intrusion kill chains will help identifying commonalities and overlapping indicators in the long run
- By matching the intrusions, we are able to recognize an intrusion campaign
- Goal of campaign analysis is to understand the intruders' tactics, techniques and procedures (TTP), focusing on their behaviour
- Being aware of trending intrusions and attack patterns, defenders can prepare their security measures according to them

## 5 Summary
- Intelligence-driven CND is necessary for countering threats, as common security measures are vulnerable to APTs
- Understanding and analyzing the threat itself is the key to a secure system
- Kill chain model helps the defender in prioritizing and preparing countermeasurements for intrusions
- Intrusion kill chain provides a guide to analyze intrusions, extract information on the threats and to defend against them

# a) Tactics, tools and procedures
- Tactic = The adversary's goal, reason for performing an action
  - ex. Credential Access, where the intruders goal is to gain a victim' credentials
- Technique = The adversary' way of achieving the goal by performing an action
  - ex. Phishing, where the intruder is going to deceive the victim into giving their credentials
- Sub-technique = a more specific desription of the technique
  - ex. Spearphishing via SMS, the intruder is going the send the victim a text message luring them into a fake website
- Procedure = The specific implementation the adversary uses for their techniques
  - ex. The intruder will first do some research on his targets, in this case his targets are some random phone numbers he found on a public phone directory
  - Then he will create a fake text message, imposing as a bank claiming that they have something "urgent" to attend to with a link to a fake website
  - He will then send the message to the phone numbers
  - The victim does not question the message and clicks the link
  - Victim enters their credentials on the website and confirms
  - Credentials get sent to the intruder
  - Intruder uses the credentials to login to the victim' bank account
  - Intruder completes his original goal and transfers the money to his own bank


## References
https://lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf

https://attack.mitre.org

https://attack.mitre.org/resources/faq/#general-faq
