---
description: Taking intelligence and applying it to cyber
---

# Treat intelligence

The goal of threat intelligence is to gather, evaluate and analysis data related to an foreign actor.\
With the intent to get better insight to the mindset of the person or more precisely the tactic technique and procedure (TTP). This will allow policy makers can make better decisions on how to mitigate risk that they pose.\
Or more simple put analyzed information about hostile intent, capability and opportunity of an adversary.\
The focus is on the threat. 

## Threat actor

Threat actor is a general term for a person or entity responsible for a cyber attack that impacts the confidentiality, integrity, or availability of an organization's assets. Most often, the term is used to describe individuals and groups that conduct malicious acts against organizations. These threat actors can be categorized as either unintentional or intentional, and internal or external.


## Threat modeling



Threat modeling is the analysis the design of a systems. To identify potential risk to security and privacy.

The purpose of performing threat modelling is to identify what can go wrong in a system by pinpointing design and implementation issue, that needs mitigation. Weather is it early in the acquirement processes or through-out it life-cycle. The output of the threat model informs decisions that you make in subsequent design, development, testing and post-deployment phases

1. Trust boundaries; location where trust or security changes
2. Data flow path; movement of data between two points
3. Input points; external input is received
4. Privileged operations; any actions that required greater privileged then standard users
5. Details about security stance and approach; declaration of security policy, security foundations and security assumptions.

### Threat modelling manifesto

[Threat Modeling Manifesto](https://www.threatmodelingmanifesto.org/)

Guidelines

* Value
  * **A culture of finding and fixing design issues** over checkbox compliance.
  * **People and collaboration** over processes, methodologies and tools.
  * **A journey of understanding** over security or privacy snapshot
  * Action over words
  * **Continuous refinement** over single delivery
* Principles
  * The best use of threat modeling is to improve the security and privacy of a system through early and frequent analysis.
  * Threat modeling must align with an organization’s development practices and follow design changes in iterations that are each scoped to manageable portions of the system.
  * The outcomes of threat modeling are meaningful when they are of value to stakeholders.
  * Dialog is key to establishing the common understandings that lead to value, while documents record those understandings, and enable measurement.



## Threat hunting

The active process of looking for signs of compromises.\
Instead of waiting for the security system to alert the security team of potential.\
The security can instead on the role as threat actor.\
What tactics techniques and procedures would you use to compromise the organization and achieve the goal wether that is exfil, ransomware or other.\
With that in mind go look for activity of the TTP you identified in the previous step.\
Once identified activity of potential malicious activity you must first verify your findings, If they are of malicious intent the next step is to activate incident response.\
The final step is to create detection rules that will alert you the next time this activity is seen in the network.

*Remember* to tune your detection rules to reduce to amount of false positive.

**From intel to threat hunting and incident response**

1. Threat model
   * Select a threat group and identify its tactics techniques and procedures (TTP) that was identified in the intel report.
2. Create a hypothesis
   * Create a testable statement related to how the threat TTP would impact your organization.
3. Hunting 
   * Once the hypothese have been created the next step is to identify the steps needed to take it prove or disprove the hypothese.
4. Learn
   * Identify gaps and opportunities of improvement.
   * Create detection rule to improve the detection of the TTP in your environment.



## Pyramid of pain

The higher up in the pyramid of pain, the more difficult will it be for the threat actor to change their behaviour.\
The goal of an threat intelligence analysis is to move as high as possible up the pyramid of pain.\
This is because the higher up the pyramid you go the more value the intel provide to other organization.

![](https://remnote-user-data.s3.amazonaws.com/g5p1PSh-1o05NUSgQmhouqlrwO9f18sqF-tml3DI0VwG9TkkqWk7Xzm6BGO3EDTf13uRFDTLFHUOpy8Smhhakct4i4OtYx\_l9ZEd6GexLn0tGt75mY\_L2hRbLe7R\_SfI.png)

## Threat feeds

It important to understand threat feeds are not intelligence, they are data feeds, and often without context why the data is in the feed. \
It up to the analysis to take the data and use it an assessment.&#x20;

Before acquiring an threat feed you need to understand why you need it, and how it relates to you.\
It important to be critical when selecting threat feeds, one of the first question to ask before acquiring is to ask about the source of the information. \
E.g if you are an company operating in Europe and the feed is from company in asia. The data might not be relevant to you.

Good way to start with threat feed is using open source like DShield, if you do not know how to handle it, you are not ready for the next level. One of the key question to ask about threat feed is the data source of the feed.


## Traffic light protocol (TLP)

Defined widely recognized threat intel protection level and who it can be shared with.&#x20;
-WIP- create your own table
_![](https://remnote-user-data.s3.amazonaws.com/a3ZQFulpDQV1Jd96ztQoQ8LY5GnnYfySNMbJ5Np-CB-ocw4DrZ\_PlG7n8jeS0NdBQbFBi69JxcYWJs5V4dSQw-Iv9\_sEOkg1XD6YA3UgfGlBJ2KSdWEj4zZygzbxe732.png)_


## Tool collection

[GitHub - IVMachiavelli/awesome-threat-intelligence: A curated list of Awesome Threat Intelligence resources](https://github.com/IVMachiavelli/awesome-threat-intelligence)


## Anaylsis bucket

Analysis bucket is an computer system that will help stored the data that is collected and have analytic tool to help understand and correlated the data.\
The reason this is important for an CTI program because of the amount of data that is required to be collected to perform good analysis over an longer period of time.\
it important to have tool that can help you both store data and interpret the data.\
Below I have written down some of the analysis bucket that exist on the market. Try them all out and see which one you like and fulfill your requirements.

Tool:

[crits]https://crits.github.io/
[misp](https://www.misp-project.org/)
[threatnote](https://threatnote.io/)
[YETI](https://yeti-platform.github.io/)
[OPENCTI](https://www.opencti.io/en/)
