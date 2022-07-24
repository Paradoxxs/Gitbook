---
description: CTI  models & frameworks 
---

# Model & Frameworks

Model and frameworks are representation of object, system or event.\ 
The reason we use models and frameworks is to take something complex and distilling it something simple. This is frequently done through categorization.

Benefits of using an framework, is that it allow one to put data into buckets.\
This will help you abstract the data and identify patterns in the data (Human fingerprint of the adversary).

This is done through structured thinking on a specific topic. Ensuring the important parts are covered. It also allow for an common language of communicate both internally and externally with other analysis.

## Cyber kill chain

Based on military concept of the kill chain Like a chain if one of the link break the whole attack fails.\
It an representation of the stages an adversary have to go through

Stages:
1. Reconnaissance
2. Weaponization
3. Delivery
4. Exploit
5. Installation
6. Command and control
7. Action

![](https://remnote-user-data.s3.amazonaws.com/-UUVtXBT5BwyuYEO0gOp1Y3sK0HBQudG3Va\_USod0cl9nkCThv9kK\_IslgBmLX4YKfmIX8x7LiEqk8ib1AZnWcWZi3xFXr6VFrPvyblzcePQFROZAKoLp5tl0jHBCZUF.png)

## Diamon model

Diamon model is an representation of the element required for intrusion.\
The model describes how an adversary deploys a capability via infrastructure against a victim Developed to be complementary to the cyberthreat kill chain For every intrusion event there exists an adversary taking a step towards an intended goal by using a capability over infrastructure against a victim to produce a result

![](https://remnote-user-data.s3.amazonaws.com/XDWmqBbConGqoXBxg5WYngqUMXyZNofQzsQtp2he2z989egpyVnfTDDQNHZbooYtXhe8mRFgRpnsjQDl1y7ZJWRUwPlNVaoF0iIXzbUT0QZGIiDohS31jitVMo2T6YNA.png)

### Adversary

Threat / Operator

One of the main problem that is seen a lot is the tracking of malware authors instead of Threat / operator

### Infrastructure

What system, network, e.g are they using to deliver their capabilities

### Victim

It important to disquiet's between victim and target.\
Just because you see an threat group in your network that does not mean your were their target. You could just be an victim they used to pivot to their true target.

## Capability/ Tactics, techniques and procedures (TTP)

The methodology the of the threat actor to achieve their objective.

### Axioms

1. In every intrusion event an adversary takes a step towards an intended goal by using a capability over infrastructure against a victim to produce a result.
2. There exists a set of adversaries which seek to compromise computer systems or networks to further their intent and satisfy their needs.
3. Every system, and by extension every victim asset, has vulnerabilities and exposures
4. Every malicious activity contains two or more phases which must be successfully executed in succession to achieve the desired result.
5. Every intrusion event requires one or more external resources to be satisfied prior to success.
6. A relationship always exists between the Adversary and their Victim(s) even if distant, fleeting, or indirect.
7. There exists a subset of the set of adversaries which have the motivation, resources, and capabilities to sustain malicious effects for a significant length of time against one or more victims while resisting mitigation efforts.

### The rule of 2

By taking specific identifier correlated on two or more verticals with the diamond model can be used to define an activity group. \
e.g. observation of a very specific capability, which communicate consistently with infrastructure, that could be defined as a activity group  &#x20;

## Mitre attack

[Mitre attack](https://attack.mitre.org/) goal is to track the  tactic used in intrusions. Categorize them into the different stages of an intrusion.\
Mitre attack also tracks what tactics the different threat groups are utilizing. Allow you to map the different TTP an specific threat group is using, to your defends matrix. With the goal to identify if you have are missing visibility and detection in your network.
