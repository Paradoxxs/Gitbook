---
description: >-
  To find evidence of user activity within digital media. answering the Who,
  what, when and how.  As evidence are recovered from the media it important to
  understand the context of the evidence, and try
---

# Digital forensics

[https://github.com/Paradoxxs/Cybersecurity/blob/master/Digital%20Forensics.md](https://github.com/Paradoxxs/Cybersecurity/blob/master/Digital%20Forensics.md)

Digitial forensic expert help to identify the:

* Motive - Why did the user perform the activity
* Means - The tools and method used
* Opportunity - How and when the activity was performed.

## Chain of Custody

Chain of Custody is the “logical sequence of gathering evidence, whether it be physical or electronic in legal cases”.\
&#x20;If this process is not followed properly, the evidence collected may be rendered inadmissible in court, so legal prosecution can’t take place.\
&#x20;Forcing prosecutors to take such a professional and cautious approach to evidence collection and storage, ensures that evidence is accurate, and has not been tampered with, so justice can be achieved. \
It is important to have a record of who collected a piece of evidence, and who has been responsible for it since it was collected. \
This means if anything happens to it, the person assigned can be held accountable.\


## Evidence

If an Analyst is conducting a forensic investigation on a hard-drive image, they should NOT be working on the original copy of the evidence. \
The original disk image should be hashed (the mathematical calculation which results in a unique text string specific to that exact file) and then a full bit copy should be taken, ensuring that absolutely everything is included in the copied image.&#x20;

This new file should then be hashed, and if it is an exact copy, the file hashes will be the same. The analyst should then work on the copy, so the original evidence is not modified, making it inadmissible in court. When copying evidence to a forensic disk (a high capacity hard-drive used only for forensic investigations or incident response), the storage media should be completely sanitised, to ensure that there is no data already on it, as this could contaminate the evidence.

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
