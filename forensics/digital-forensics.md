---
description: >-
  To find evidence of user activity within digital media. answering the Who,
  what, when and how.  As evidence are recovered from the media it important to
  understand the context of the evidence, and try
---

# Digital forensics

Digital forensics is a branch of forensics science encompassing the recovery and investigation of material found in digital devices, often in relation to computer crime. So, Forensics is the technical process of recovering or collecting evidence that will be used in an investigation. In regards to Security Operations, this discipline is often associated with monitoring of employees to maintain a high-security posture, aiding with incident response to reveal details of how a compromise occurred and any post-actions (known as DFIR), as well as other tasks which require a ‘deep-dive’ into technical aspects.

Digitial forensic expert help to identify the:

* Motive - Why did the user perform the activity
* Means - The tools and method used
* Opportunity - How and when the activity was performed.


## Digital investigation plan

Using the scientific method for forensics.
Before you begin any forensic investigation you need to have an clear question that you are seeking out to answer.
The next step is to create an plan how what are you doing to investigate and how are you going to analysis the data.

Take all the information you found and list out the information the prove or disprove the question you are trying to answer.

#### What is forensically sound

* Consistent
* Repeatable
* Well documented



## Type of forensics

#### Data artifact

* BIOS
* Unified extensible firmware interface (UEFI)
* RAM
* Logs
* Infrastructure logs (router, switch, firewall, etc.)
  * Windows : C:\windows\Systems32\config
* Network attack storage (NAS)
* Harddisk
  * Mapped drives
  * Universal naming convention (UNC paths)
* IOT
  * Where is the data and who do you acquire it
* Cloud storage
* Removeable drive
  * What removeable devices have been connected to the computer This can include usb drives, external hard drives, phone and tables.
* Unorthodox
  * Private cloud
  * P2P network
  * Virtual hard drives
  * Virtual machines
  * Encrypted contained

### Computer Forensics

* Identifying, collecting, and preserving evidence taken from desktops, laptops, and other computer systems and storage media for the purpose of aiding investigations or legal proceedings.

### Network Forensics

* The monitoring, collection, and analysis of network activities such as visited websites and connected IPs, usually associated with incident response and intrusion detection.

### Memory Forensics

* The process of recovering evidence from the RAM of a running system (also known as live acquisition or live response).

### Mobile Forensics

* The process of recovering evidence from mobile phones, SIM cards, PDAs, tablets, and other mobile devices.

### Communication

The process of recovering evidence of communuication between two or more people

### Location history

Identify location data of where the subject have been

## Chain of Custody

Chain of Custody is the “logical sequence of gathering evidence, whether it be physical or electronic in legal cases”.\
If this process is not followed properly, the evidence collected may be rendered inadmissible in court, so legal prosecution can’t take place.\
Forcing prosecutors to take such a professional and cautious approach to evidence collection and storage, ensures that evidence is accurate, and has not been tampered with, so justice can be achieved. \
It is important to have a record of who collected a piece of evidence, and who has been responsible for it since it was collected. \
This means if anything happens to it, the person assigned can be held accountable.\

## Investigative plan

The goal of having an investigation plan is not to mindlessly during full forensics of the device. Instead to an clear outcomes and an process to arrive at that outcome.

Have clearly define hypotheses that you are seeking out to prove or disprove. 
Once you have define that. The next step is to create an roadmap for you to follow where the you think the relevant information will be.



## Evidence



### Handling evidence

It important when analysis is working on evidene that only an copy of the evidence.\
This way it always possible to go back to the original evidence to see if anything have been altered during the analysis process.\
The way evidence is compared is by using cryptographic hashes&#x20;

#### Computer

Evidence will be files and other data on electronic storage media, such as hard-drives in desktops, laptops, and mobile devices

#### Network

Network devices such as a web proxy or router, e.g. will also hold information about network connection, requested sites, etc.

#### Mobile devices

The wealth of information on our phones is include, and can be very useful to investigators. Evidence such as call history (incoming/outgoing/number/duration), text messages, contacts, web history, images, videos, apps, GPS location, notes, and much more can be retrieved Handling evidence using Chain of custody

#### Forensic snapshots

For mission critical internal servers and serves exposed to the internet, your efforts also should include creating periodic system snapshots. It a collection of data that documents the configuration and running state of the machine at a point in time.

Its purpose is to provide a baseline against which later snapshot can be compared in order to detect changes. Presumably, we have a before snapshot, when we assume the machine is working fine and there have been no been compromis, and an snapshot taken after problems began or after a suspected compromise.

The before and after snapshots can be compared so that only the differences are listed. This process is useful for troubleshooting, but we mainly wish to use these snapshots to detect intrusions, to know how our adversaries have modified our systems, and provide forensics evidence that might be admissible in court of law.

## Timeline analysis

Timeline analysis is **the process of collecting and analyzing event data to determine when and what has occurred on a computer for forensic purposes**.\
You begin with the pivot point which is what occurred immediately before and after the event (Temportal proximity). The reason for using pivot point is because it gives you an instant look at what happend on the system around the time of the event.

When recovering artifact it important to see the context surrounding the artifacts to accurately understand the evidence.

### MACB

* Data modified (M)
  * Time the data content of a file was last modified
* Data access (A)
  * Approximate time when the file data was last accessed
* Metadata changed (C)
  * Time record was lasted modified
* Metadata creation (B)
  * Time file was created in the volume / directory

### Determine Pivot point

* ![](https://remnote-user-data.s3.amazonaws.com/MgOUyXq65GKIihqdzteRpjATFhtybE\_xMeXSX1I56CBf\_UgdYKEKVr0bCuqUjKNboDL5\_AaFpYG\_Ta1-SRQsZwXBfHQ8du13mEyW2aGd3u7WEYZpw8BVxvtUsE9VB\_wa.png)

### Process

* Timeline scope : what question need to be answered
* Narrow pivot points : time-based, file-based
* Determine the best process for timeline creation
  * Filesystem-based timeline
  * Super timeline creation
* Filter the timeline
* Analyze the timeline - Focus on the context of the evidence.



## Detecting Evidence destruction

The process of looking for signs of tampering of the device or data, with the purpose of removing the evidence of one activity.

There are many ways of detecting tampering of evidence, the most common once are lack of usage data, created date, database inconsistency.

* Change hardware components
  * SMART
    * Hardware operation metrics, e.g. how long it have been in used, etc.
* Deleting files
  * File carving
* Clearing cache
* Removing application
* Selectively deleting messages or history
* Wiping device
  * Lack of usage
* Modifying files to advoid detection.

## Research

This is a very important part of digitial forensics because of how fast technology change.\
The purpose is to understand new technology and application to allow one to extract and understand user activity.\
An good way to learn forensics methods is to read reach journal



Sources:

* [Digital Investigation - Journal - Elsevier](https://www.journals.elsevier.com/digital-investigation)
* [Digital Investigation | Journal | ScienceDirect.com by Elsevier](https://www.sciencedirect.com/journal/digital-investigation)
* [The Journal of Digital Forensics, Security and Law | Journals | Embry-Riddle Aeronautical University](https://commons.erau.edu/jdfsl/)
* [IEEE Security & Privacy | IEEE Xplore](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=8013)
* [DigitalFIRE Labs – DigitalFIRE is a research laboratory based in the University College Dublin School of Computer Science and Informatics.](http://dfire.ucd.ie/)
* [Google Scholar](https://scholar.google.com/scholar?hl=da\&as\_sdt=0%2C5\&q=digital+forensics\&btnG=)
