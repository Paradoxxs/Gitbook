# Overview

The reason why we reverse engineer objective is to get better insight into the functionality of the software in question.\
This is done by breaking the software into code.\
This is done by an disassembler tool to break the software into a low level programming language such as assembly, Or back to source code as with C#, Java, and etc. 

In this book I will talk about two purpose of reverse engineering.\
The first is for malware analysis. To break the malware apart to better understand the function of the malware. This could be for multiple reason to understand how the malware perform its C2 communication, or with ransomware to understand the encryption alogroithm used and see if the encryption key is located within the software or and weakness of the encryption implementation.\
Allow one to decrypt the files without having to pay the threat actor.\
An other goal with malware analysis is to create config extractor. Most threat group are using malware they have bought off the blackmarket, and the only difference between their version and other is the configuration of the malware. This could the IP or domains used C2 communication, the message left behind the threat actor, and etc.\
The goal of creating an config extractor is to automate the process of extracting this information from malware. Allowing one to response faster to incidents.  

The other is for forensics reason. This is common for mobile applications. Were you must understand the context of the information around an mobile application. To break about the different function of the application. To understand how information is stored. The format of the stored data.\
With application that have encrypted their storage it could be to understand the encryption algorithm. Allow you to extract the information from the data storage.\
Once done the next step is to automate the process of extracting information from applications.\
Allow the forensics team to quick extract information from applications. 

