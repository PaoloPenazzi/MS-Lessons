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

> ### What is physical security? Make some examples.

???

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
> ### Multi-factor authentication: pros/cons and the threats to this model.

Each type of authentication has its own weakness. Multi-factor authentication consist of combining two or more types of authentication to increase security.

So in practice two (or more) steps are used to verify the identity of an entity that is trying to access services. For example: a memory card plus a pin to remember.

We need to use two different channels for each type of factor: if we use two factor, both involving our PC, what happen if our PC is compromised?
> ### Smart cards vs memory cards: differences, how does it works and threats.
> ### Definition of password crackers, examples and how to use them to attack and defend.


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

## Tutorials
### John the Ripper


