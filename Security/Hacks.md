# Hacks
The term "hack" is used when describing a clever trick or workaround that may not be the most elegant but gets the job done effectively.
When applying this term to computer system security this 'workaround' can pose [[Security Threat]] to systems and data.
## Malware
short for "malicious software"
This is a type of [[Hack]] that uses a piece of software to perform dangerous and harmful actions.
Mechanisms for propagation:
- Human Behavior and Social Engineering
	- [[Phishing]]: Malware can spread through phishing emails or SMS tricking users into clicking links or downloading attachments.
	- Social Engineering: Manipulating users to download fake software or giving away credentials.
- Exploiting Software Vulnerabilities:
	- Gaining unauthorized access to systems.
	- Drive-by Downloads: code that's automatically downloaded and executed when a user visits an unsafe website.
- Automated Propagation Techniques:
	- Network Propagation: When malware scans and infects other vulnerable systems within a network, using similar vulnerabilities.
	- Self-Replicating Malware: Example of this are [[Worms]], which are designed to replicate across computer networks without user control.
	- USB/Removable Media: Often called a 'rubber ducky' its a USB drive or other removable device, that hosts malware which will execute when plugged in.

Different forms of malware are:
[[Viruses]] 
[[Trojans]] 
[[Ransomware]]
[[Spyware]]
[[Adware]]
[[Worms]] 

## Phishing
Phishing is a form of [[Security Threat]] where malicious actors deceive people into providing sensitive information.  
Spear-Phishing attack is a specific person
Whaling is when you target an important person
### Distribution
- ubuntu is a way to distribute a hacking attack
- People often grab a large email list
### Email
- The goal is to make an email that look legitimate so someone will download something or click a link.
- Making a phishing email is super easy, but getting a legit looking domain is harder
- People can hover over links in email to see where they go
### Credential Stealing
- clone black eye, the repository
- nGrok account to host the site we are giving the target
- the website then refreshes to the actual page and logs them in
### Downloading Files
- DNS poisoning, you can change the **host file** so that it redirects to a different IP address, even when you type in the right address it will redirect you.
### Protection
- Spam filters
- Clicking links is dangerous
- It could be texts as well, voting texts
- Invoice scams are pretty effective
## Worm
Self-replicating [[Malware]] that spreads across networks without needing human interaction. Worms can consume network bandwidth, degrade system performance, and deliver payloads like viruses or ransomware.
## Virus
A type of [[Malware]] that replicate themselves by attaching to other files and programs, spreading from one system to another.
## Spyware
[[Malware]] designed to secretly gather sensitive information from a system and transmit it to the attacker.