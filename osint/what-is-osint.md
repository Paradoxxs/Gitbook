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

-WIP-

## OSINT cycle

![](<../.gitbook/assets/image (1).png>)



Requirement gathering

* What are the question you are seeking answers to.

Retrieving data

* Search and collect data about the target.

Analyzing data

* Transform data into information through analysis.

Pivoting & reporting

* pivoting data to other data, and reporting the data to the customer.

## Documentation

Documentation is key, you never know if the information get removed or the sites get taken down, Or you might simply not being able to to find the information again.&#x20;

* Tools
  * hunch.ly
  * Microsoft steps recorder
  * Windows gaming recording (win+g)
  * FastStone
  * Snagit

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
