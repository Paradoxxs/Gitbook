# Overview



## Methodology

99% of forensic analysis focuses on 1% of the data. Steps

1. Image RAM
2. Check for disk encryption
3. Create quick triage image
4. Begin analysis of triage image
5. Image entire hard drive
   * Only if necessary

## Process

### Live response

* Dump memory
* Check for encryption
  * If encryption is in place, image acquisition should be done before system get shutdown.

### Deadbox acquisition

#### Media removal

Beware of servers as the drive does not work like a laptop, they could be in a RAID configuration, in these cases, it would be better to boot up the devices and transfer data out that way.

The same problem is present with closed case devices like Surface Pro and mac. This is where secure boot comes into play.

### triage collection

Taking an copy of selective files on the computer, that relevant to the case.

### Imaging

Taking an complete image of the disk

### Mounting

Allowing to access the drive like any other drive, allowing one to interact with the information without being tied to a specific forensics tool.

### Notes

#### Unallocated space & Non-Standard volumes

Some forensics tools have the ability to export the data, It is important to verify if the tool in usage can export data from these kinds of volumes.

#### Multi-drive storage

Not always a physicals interface to interact with it. Often is has a web-portal, API or other interface. Because of the way multi-drive storage solution store data it not feasible to extract the drive, which is way these solution should be interacted with in the proper way.

#### Write block

Everytime you interact with the orginal evidence write blocker must be used to prevent any changes to happen to the storage device. There exist two types hardware and software blocker. Hardware should be used is possible, software is the second choice.
