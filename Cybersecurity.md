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

Passive attacks attempt to learn or make use of information from the system but do not affect system resources.

Example: eavesdropping or trasmission monitoring. (message contents, traffic analysis).

Passive attack are difficult to detect, so the countermeasure emphasis is put on prevention rather than detection. 

Active attacks involve modification of the data stream (or the attacked system).

Example: masquerade, replay, modification of messages, denial of service.

The countermeasure goal of active attack is to detect and to recover.

