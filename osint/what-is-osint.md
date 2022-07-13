---
description: >-
  Process of using the open source public available data, to gather information
  about an specific target.
---

# What is OSINT

OSINT as a source is an great way to discover information about an target organization or individual. \
Working out what systems a company uses. User information can be harvested, allowing potentially effective social-engineering vector.

It important before you even start your journey into OSINT that you have your methodology in place.

## Methodology

### preparing

Before you even begin you need to prepare to work environment. Identify and organize your resources so they are ready for action. It will also allow you to identify if you are missing sources of information.
Setting up sock puppet account on the different social media and forums.


### Request for information

An set of procedure to help you perform an OSINT investigation.

Before you begin on your OSINT investigation you need to is an request for information (RFI). This question can come in many forms some of the more common once are **Threat assessments** monitoring of group or individual what their capability and intent. It also allow you to set clear expectations with the customer.

**Target profiling / attribution** unmasking an profile online and offline presences, identifying the real person behind online personas.

### Planning

Assessing the current situation, planning the approach that will yield the best result and answer the question set forth by the customer. Allowing you to move forward with a purpose rather than just whack-a mole through the internet.

To make this step easier, it an good idea for how an set of workflow that describe how you are going to conduct an investigation based on the information available. E.g IP address what tools, tactics and procedure do you have for gathering additional information.

### Documentation

Now is a good stage to start the documentation processes.
Documentation is key, you never know if the information get removed or the sites get taken down, Or you might simply not being able to to find the information again.&#x20;

Create your workspace for the specific case. Help you ensure that the difference cases your are working on does not get mixed up. Start by adding the communication the lead up to the request and the agreed upon request for information.

One product might not be enough to do everything. I like to use multiple tools. Note taking application, graph drawing program allow you to visualize information. Some of the common once are Microsoft OneNote, xmind,  

Tools
* hunch.ly
* Microsoft steps recorder
* Windows gaming recording (win+g)
* FastStone
* Snagit
* OneNote
* Xmind

## Reporting

This is what you gets paid for creating the report of all the information that have been collected and the intelligence analysis you have performed.How the report is structure is up to you. I like the order of:
* Request for information
* Conclusion
* Analysis
  
This structure will allow the reader to quickly see what was the information request and the conclusion, if they want to dive into how we got into the conclusion they can do so in the analysis part. 


Archive the investigation so it does not get mixed in with future work. One way to do if working from an VM is to create an snapshot, which you can return if need to continue the investigation.

### OSINT cycle


Requirement gathering

* What are the question you are seeking answers to.

Retrieving data

* Search and collect data about the target.

Analyzing data

* Transform data into information through analysis.

Pivoting & reporting

* pivoting data to other data, and reporting the data to the customer.



## Securing yourself&#x20;



### Virtual machine

You never know what sites you are going to visits, they might be trying to infect your system,\
Which is the reason for using an dedicated machine for OSINT which can be thrown away if it gets infected by anything.\
I have choosen to use virtual machine, they are inexpensive, and easy to setup. \
They also allow you to keep dedicated machines to every case, there by reducing the chance for having information from one case leak into another one.&#x20;



#### Software

{% embed url="https://www.vmware.com/products/workstation-player.html" %}

{% embed url="https://www.virtualbox.org/" %}

#### Images

Some of the images I have used over time. you can also use a base image like Ubuntu and create your own OSINT workspace.

{% embed url="https://www.tracelabs.org/initiatives/osint-vm#downloads" %}

{% embed url="https://csilinux.com/download/" %}

{% embed url="https://www.kali.org/get-kali/" %}

### Virtual private network - VPN

List the best VPN service [https://app.gitbook.com/s/CbkXHDJVY24oY6Zl0jpY/\~/changes/XPSlryFfuo0a2OUB2T5v/forensics/windows/network-activity](../forensics/windows/network-activity.md)

Setup your own VPN with Streisand\
[https://github.com/StreisandEffect/streisand](https://github.com/StreisandEffect/streisand)
