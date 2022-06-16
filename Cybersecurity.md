# Domande Cybersecurity
## Overview
> ### Difference between system integrity and data integrity.
Integrity is one of the 3 key concepts of the CIA Triad

**System Integrity:** assure that a system performs its intended function in an unimpaired manner, free from deliberate or unauthorized manipulation of the system.

**Data Integrity:** assures that information and programs are changed only in a specified and authorized manner.

This means guarding against improper information modification or destruction. Including ensuring non-repudation and authenticity.

> ### Fail-Safe Default: what is, which are the pros/cons and an example. 

**Fail-Safe Default:** means access decision should be made based on permission rather than exclusion. The default situation is lack of access, and the protection scheme indentifies conditions under which access is permitted.

Example: we want to register a guest user in the system. When we create this new guest account it won't have any permissions. This is why is very secure. 

If we apply this approach the problem is that when a user needs a system resource, we should give him the permission to access it. So we lose some usability but we gain a lot in term of security.

> ### Explain what is an attack tree.

Attack trees are often used to perform attack surface analysis.

An attack tree is a branching, hierarchical data structure that represents a set of potential techniques for exploiting security vulnerabilities. 

Objective: to effectively exploit the info available on attack patterns (Example: the moethods used to find errors or problems in the systems)

Attack trees can be used by the security analysts to guide design and strengthen countermeasures.

> ### What is Accountability? Make an example.

The security goal that generates the requirement for actions of an entity to be traced uniquely to that entity.
It's necessary to support: non-repudiation, deterrence, fault isolation, intrusion, detection, prevention, recovery and legal action.

Example: ability to find the originator of a transmission, a message, or an action.

> ### Difference between data confidentiality and privacy.

Confidentiality is one of the 3 concepts of the CIA Triad

**Data Confidentiality:** Assures that private or confidential information is onot made available or disclosed to unatuhorized individuals.

**Privacy:** Assures that individuals control or influence what information related to them may be collected, stored and by whom and to whom that information may be disclosed.

> ### What is unauthorized disclosure? Explain exposure, interception, inference and intrusion.

Unatuhorized disclosure is a circumstance or event whereby an entity gain access to data for which the entity is not authorized.

**Exposure:** Sensitive data are directly released to an unauthorized entity.

**Interception:** An unauthorized entity directly accesss sensitive data travelling between two authorized entities.

**Inference:** A threat action whereby an unauthorized entity indirectly accesses sensitive data (not 
necessarily the data contained in the communication) by reasoning from characteristics or by-products of communications.

**Intrusion:** An unauthorized entity gains access to sensitive data by circumventing a system's security protections.
> ### Active and Passive attack: definition, differences, example and countermeasure.

Passive attacks attempt to learn or make use of information from the system but do not affect system resources.Example: eavesdropping or trasmission monitoring. (message contents, traffic analysis).

Passive attack are difficult to detect, so the countermeasure emphasis is put on prevention rather than detection. 

Active attacks involve modification of the data stream (or the attacked system).Example: masquerade, replay, modification of messages, denial of service.

The countermeasure goal of active attack is to detect and to recover.

## Crittography
> ### Difference betweeen brute-forcing and cryptoanalysis.

Cryptanalytic attacks rely on the nature of the algorithm plus perhaps some knowledge of the general characteristics of the plaintext. This type of attack exploits the characteristics of the algorithm to attempt to deduce a specific plaintext or to deduce the key being used.

The brute-force attack, consists of trying every possible key on a piece of ciphertext until an intelligible translation into plaintext is obtained. On average, half of all possible keys must be tried to achieve success. Unless known plaintext is provided, the analyst must be able to recognize plaintext as plaintext. This is why to supplement the brute-force approach, some degree of knowledge about the expected plaintext is needed, and some means of automatically distinguishing plaintext from garble is also needed.

> ### Asymmetric Encryption

A public key encryption scheme has 6 ingredients:

Plaintext: This is the original message or data that is fed into the algorithm as input.

Encryption algorithm: The encryption algorithm performs various substitutions and transforma- tions on the plaintext.

Public and Private key: This is a pair of keys that have been selected so if one is used for encryption, the other is used for decryption.

Cyphertext: This is the scrambled message produced as output. It depends on the plain text and the key. For a given message, two different keys will produce two different ciphertexts.

Decryption algorithm: This is essentially the encryption algorithm run in reverse. It takes the ciphertext and the secret key and produces the original plaintext.

> ### How can you send an email guaranteeing authenticity? Include technical steps and theoretical considerations and threats.

???

> ### Weak vs. strong secure hash function.

A strong hash function has the following properties:

* H can be applied to a data block of any size.
* H produce a fixed-length output
* H(x) is easy to compute for any given block of data x, making both hw and sw implementations practical.
* For any given code h, it is computationally infeasible to find x such that H(x) = h. (**One Way**)
* For any given block x, it is computationally infeasible to find y != x with H(y) = H(x). (**Second pre-image Resistant**)
* It is computationally infeasible to find any pair (x, y) such that H(x) = H(y). (**Collision Resistant**)

If only the first 5 properties are satisfied, it's a weak hash function.
If all the above properties are satisfied, it's a strong hash function.

Example of use:
* **Password:** The system stores only the hash of passwords
* **Intrusion Detection:** Compute nad securely store the hash of relevant files int the system. Providing integrity.

> ### Digital Signature and public key certificate.

Digital signature is used for authenticating both source and data integrity. Created by encrypting hash code with private key.

Does **not** provide confidentiality: the message is safe from alteration but not eavesdropping.

Public key certificates are an example of digital signature.

An user (Alice) wants to publish it's public key. But everyone can act like Alice and publish a public key. So we need to find a way to verify that the public key is really the Alice's public key.

To do so Alice creates a pair of key (one public and one private). She creates an unsigned certificate containing her userID and the public key. This certificate is sent to a CA (certificate authority) which is a trusted entity. The deliver of the certificate requires a face-to-face meeting or a phone call to verify that the certificate is really from Alice. The CA add to the certificate its information and then encrypt the hash of the certificate with his private key and returns the certificate to Alice.

Alice can now publish the public key with the certificate and if another user wants to verify the authenticity of the certificate can do it by decrypting the certificate using the CA's public key.

## User authentication

> ### Password selection strategies.

When not constrained, many users choose a password that is too short or too easy to guess.

* **User Education:** This strategy is unlikely to succeed at most installations, particularly where there is a large user population or a lot of turnover. Many users will simply ignore the guidelines. Others may not be good judges of what is a strong password.
* **Computer-generated passwords:** This also have problems. If the passwords are quite random in nature, users will not be able to remember them. Even if the password is pronounceable, the user may have difficulty remembering it and so be tempted to write it down.
* **Reactive password checking:** strategy is one in which the system periodically runs its own password cracker to find guessable passwords. The system cancels any passwords that are guessed and notifies the user. (Resource intensive and still slower than the attacker)
* **Complex password policy:** In this scheme, a user is allowed to select his or her own password. However, at the time of selection, the system checks to see if the password is allowable and, if not, rejects it. Such checkers are based on the philosophy that, with sufficient guidance from the system, users can select memorable passwords from a fairly large password space that are not likely to be guessed in a dictionary attack.

> ### Token-based authentication: types, how does it works, pros/cons, threats.



> ### Difference between remote user auth and local auth. Possible threats and countermeasures.

Local authentication means that the user attempts to access a system that is locally present.

Remote user authentication is a more complex case: takes place over the Internet, a network, or a communications link. Remote user authentication raises additional security threats, such as eavesdropping, capturing a password, replaying an authentication sequence that has been observed.

To counter these threats usually we relies on some form of challenge-response protocol.

1. Client send to the server its UserID
2. Server respond with a random number (r), hash function (h) another hash function (f). (r, h(), f())
3. Client apply the first hash function to the password, and the second hash function to the result of the firt one plus the random number. f(r', h(P'))
4. Server checks if the client response is equal to f(r, h(P(U)))

> ### Password vulnerabilities countermeasures.

There are different countermeasure that could be used:

* Controls to prevent unauthorized access to the password file.
* Intrusion detection measure.
* Rapid reissuance of compromised password.
* Account lockout mechanism. (The account is locked after a given number of failed attempt: useful, but could be abused for example by a DoS)
* Policies to inhibit users from selecting common passwords
* Training and enforcement of password policies.
* Automatic workstation logout.
* Policies against similar passwords on network devices.

> ### Multi-factor authentication: pros/cons and the threats to this model.

Each type of authentication has its own weakness. Multi-factor authentication consist of combining two or more types of authentication to increase security.

So in practice two (or more) steps are used to verify the identity of an entity that is trying to access services. For example: a memory card plus a pin to remember.

We need to use two different channels for each type of factor: if we use two factor, both involving our PC, what happen if our PC is compromised?
> ### Smart cards vs memory cards: differences, how does it works and threats.

They're both physical tokens.

Memory cards can store but not process data. It can be used alone for physical access (Hotel room card). 
Provides significantly greater security when combined with a password or PIN (Bancomat)

There are some drawbacks: requires a special reader, the token could be lost, information are often stored in clear.

Smart cards include an embedded microprocessor.

Two types of interface:

* Manual: include a keypad and a display for interactions.
* Electronic: communicate with a compatible reader/writer.

Three types of authentication protocols:

* Static. (bad in terms of security)
* Dynamic password generator. (requires some type of synchronization)
* Challenge-response protocol.

> ### Definition of password crackers, examples and how to use them to attack and defend.

## Access Control
> ### Mandatory Access Control System.

The goal is to prevent any illegal flow of information through the enforcement of multilevel security.

Typically used in military security, it uses a label mechanism. Each resource is stricly classified in security levels (Top-secret, secret, confidential...)

The main drawback is that it's very rigid: this is why it's applicable in only few environment.

A system user cannot change the level of security of a resource neither give access to another user. All the changes can be made only by the system administrator.

Compartment: Each resource may be associated with a project, called compartments.

> ### Access Control policies: sicurezza, performance.
> ### Role-based access control: what is, usability, implementation, performance.
> ### Discretionary Access Control System.
## Hardening
> ### What is physical security? Make some examples.

Physical security is a fundamental part of most security policies: compromised device are hard to detect, and compromission can be both hw and sw.

Encryption techniques for hardening commonly require the management and secure storage of secret keys.


## Readings
### The IoT is widely insecure.
> ### Resume

The problem with IoT starts from how the embedded system market works.

This systems are powered by cheap processors made by company like Broadcom or Qualcomm. These manufacturers throw on the chip a light version of Linux (often outdated) and they do as little engineering as possible before shipping the product.

System manufacturers, who often doesn't get their name on the finished product choose a chip based on price and feature and build a router, server, or whatever. They don't do a lot of engineering, either.

The brand name company usually add a UI and make sure everything works and they're fine too.

No one has any incentive, expertise or even possibility to patch the software once it's shipped. 

When these devices are new, the software is already old. After few years things are even worse. Many of the device drivers are usually binary without the source code, so they can't be patched.
And even if a patch is available, it's up to the user manually download and install it. But no one alert the user that a patch is available.

The result is hundreds of millions of devices that have been sitting on the Internet, unpatched and insecure, for the last five to ten years.

Internet of Things will only make this problem worse, as the Internet becomes flooded with new embedded devices that will be equally poorly maintained and unpatchable.
Some years ago we only had PC connected to the internet, now we will have more device, and so, more vulnerabilities.

> ### My idea

I think this is an understimate problem: no one talk about that. Until i read this article i've never thought about that.
I think we must put a lot of effort to make the people aware of this problem, and educate them to care about the security of their devices.
But this is not enough. We must harden the requirements for the chips that are produced: no more obsolete software, no more binary-blobs but open-source code. When the manufacturer sell a chip it must reach a high level of security. Same thing goes for the ISP: they must be responsible to alert the user to update their product or to update it.

### Trusting trusts

### Internet worm incident

A worm is a program that can run independently and can propagate a fully working version of itself to other machines.

A virus is a piece of code that adds itself to other programs, including operating systems. It cannot run indipendently: it requires that its "host" program be run to activate it.

The worm took advantage of flaws in standard software installed on many Unix systems:

* fingerd and gets: the finger program is a utility that allows user to obtain information about other users. It is usually used to identify the full name or login name of a user. The bug exploited to break fingerd involved overrunning the buffer the deamon used for input. The gets call takes input to a buffer without checking for bounds on the buffer involved.
* Sendmail: The sendmail program is a mailer designed to route mail in a heterougeneous internetwork. It operates in several modes, the one exploited by the worm was the deamon (background) process. The Worm would issue the DEBUG command to sendmail and then specify the recipient of the message as a set of commands instead of a user address. This feature is useful for tester, but is often left on by system administrators.
* Passwords: A key attack of the worm program involved attempts to discover user passwords. It was able to determine success because the ecrypted passwor dof each user was in a public-readable file. The Worm used such an attack to break passwords. It used lists of words, including the standard online dictionary, as potential passwords. It encrypted them using a fast version of the password algorithm and then compared the result against the contents of the system file.

The Worm consisted of two parts: a main program. and a bootstrap or vector program. The main program. once established on a machine, would collect information on other machines in the network. to which the current machine could connect. It would do this by reading public configuration files and by running system utility programs that present infonnation about the current state of network connections. It would then attempt to use the flaws described above to establish its bootstrap on each of those remote machines.

Once established on the target machine, the bootstrap would connect back to the instance of the Worm that originated it and transfer a set of binary files (precompiled code) to the local machine. Each binary file represented a version of the main Worm program, compiled for a particular computer architecture and operating system version. The bootstrap would also transfer a copy of itself for use in infecting other systems.


### Voting

The idea of electronic voting has gained significant ground in the past few years, but it’s far more complex than it appears at first.

* Accuracy: we want the final vote count to accurately represent the choices of the people.
* Verifiability: it’s important to be able to check the accuracy of the vote and determine whether an election has been tampered with. If any manipulation is found, a new election can be conducted.
* Anonymity: the need for anonymity in voting is complex, because we don’t want anonymity in all aspects. We need to be able to verify who is voting in order to prevent people from voting multiple times or committing other types of fraud. However, we want the votes themselves to be anonymous. If the government, opposing party, or anyone else could find out who an individual voted for, it may lead to intimidation or coercion. This would compromise the integrity of the vote.
* Accessibility: needs to take all voters into account. It would be great to allow everyone to vote from the comfort of their own homes to make the process easier. At the same time, we don’t want a system that is too technical and makes it difficult for some segments of the population to vote.
* Speed: it’s best if we can receive the results in a relatively short period of time. If it took a year to calculate the final vote tally, the will of the people at the time of the results may be very different from what it was at the time when the votes were cast.
* Cost-effectiveness: we could have the most secure or accurate system in the world, but if it costs 10 times a nation’s GDP to implement, it wouldn’t be practical.

One of the main issues is that many of these properties compete against each other. If you make the system excessively secure, it may also be too hard to use for most of the population. You could also build a system that is incredibly fast but has a high error rate. 

There are 2 types of electronic voting: E-voting and I-voting.

E-voting still takes place at central polling locations, with observers overlooking the process. The difference between e-voting and paper voting is that e-voting involves using technology in any of the voting processes.

Remote e-voting, also known as i-voting, uses the internet to allow people to vote from essentially anywhere. It can be done with computers, smartphones and other devices. It’s probably what most people think of when they hear the term electronic voting.
I-voting has the most appeal, because participants don’t have to leave their home to vote. 



## Tutorials
### John the Ripper


