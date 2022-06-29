---
description: Deadbox location for finding evidence
---

# 🖥 Windows

## **File system**

![](https://remnote-user-data.s3.amazonaws.com/oKYqnYAWVmPJq0\_n3qgR5vkO5AECFzLzbVxlGEFwx7EkfWOYcfXGmyLzbaeEzbj5yiwCxmaQeqRLuOkiGOOz39z\_GrOiWrTFqOb38Cr0athdQ5g4NXKCvIwGODSO9a-v.png) ![](https://remnote-user-data.s3.amazonaws.com/0gR4D8dVplvyc1Pd0XoHdk\_EhFHC0hg9cbS9yGILLSI8dCyqI\_4d0ZjOXCeejuUQA-rKvimIoGN-ZjkXR1yTuygyrqHnSTm-qGVaiVhxnaidBCYi5UBDDbHmiU3I9nAx.png)

### **NTFS (New technology file system)**

#### **Allocated and Unallocated cluster**

**Allocated**

Data block is actively being used by a file

**Unallocated**

Data block is not being used by a file The data is still exists on disk and is fully recoverable until the unallocated space is overwritten

#### **Master file table (MFT)**

Tracks all object that object that is saved to the NTFS volume, where every object gets a file record within the MFT that stored various data and metadata related to the file. Both file, directories and volume name get it own record.

Where each file gets a 1024 byte long record, if the file is small enough the content will be help within the MFT, otherwise there will be a pointer to a cluster which contains the file content.

By default, MFT reverse 12.5 % of the disk, if the other 87.5% of the drive become full first then MFT section will be halved.

The 24 first entries are reversed for the NTFS volume, where the 12 first are used to make NTFS work, and hidden unless view by speical tools.

#### **Alternate data stream zone identifier (ADS)**

Alternative content for the file, which exists by creating additional data points within the NTFS file.

One of the key thing about ADS is the ability to tell the source of the data as it will be store in the information inside ADS named zone.Identifier If the zone.Identifier is not present, it most likely came from a storage device with the fat format.\
zone.identifier have a zoneID which will tell the type of source the file came from.

```
NoZone = 1 MyComputer = 0 Intranet= 1 Trusted= 2 Internet= 3 Untrusted= 4
```

Will not be lost if file get transfer to other file system

ZoneID=3

Downloaded from the internet. URL of the downloaded file might also be present here.

#### **Volume shadow copy**

Allows the user to restore to previous version to a given point. Can allow a forensic expert to analyze the previous backup of the device.

#### **Time**

NTFS records four timestamp for file and folders.\
The time precious is down to 100ns since jan 1st 1601 \
Type four timestamp:

1. Last modify time for file
2. Last access for file
3. Last modification of MFT record
4. File creation time of MFT record





### FAT (File allocation table)

![](https://remnote-user-data.s3.amazonaws.com/B0mXvuoyfYJKHPRfTgqNLdO1nbML5zwMxU\_EOec6L9pDbltwT7u8gt0VWtPATispwR3l0\_q64O9BXyoZO5ZMn8JhL4p0J3ohZTGoypBNsU9jhanm1R5xp\_KGmDmkq9Ce.png)

Widely supported across platform and must simpler than NTFS Allows for system independent data sharing

![](https://remnote-user-data.s3.amazonaws.com/KcJWUreleK8dWEISWFKlnp\_QcxqYGrt5ktiTrWjEqqTx5sSqPaRrFC\_uv1hmAOvIsVJiXe-KCWGSYItrM\_Mm5a55V9q3f30fDVjXZ16d8NfzCWfUTPOjd7lxphsVuK8C.png)

Boost sector

* Bytes per sector, Sectors per cluster, Volume name, Serial number Fat 1 & 2
* Tracks each cluster on volume, fat2 is a copy (backup) of prime fat Root folder
* Tracks files and directories at root volume



## Registry

The registry is a collection of database files which stores configuration data of the system.

The database entries consist of a key, valuetype, value and last write time (UTC). There are four root database files

![](https://remnote-user-data.s3.amazonaws.com/ZX\_i7A12pxrZLyUYpkR3WqZ9u91rHQoduJCCgvN\_XYrhiONpPRWLKe43ZGfTmJzyU7Ck902ZRurY7QTh27of4elkk0cFBB1PKWxwE-eGJrKwlzzGoVRgGJBA-8wTNgJI.png)

### Transaction logs

Transaction log file contain data that have not been written to the registry hive, cache registry data prior to permanently being written to hive file. The cache get flushed at least once per hour or when the system is not being used.

### Backup

Backup of the registry are location at C:\Windows\System32\Config\RegBack. backup are made every 10 day.

#### Most recently used (MRU)

Show the temporal order of values in key from newest to oldest.

#### Deleted registry

Because registry is a database it difficult to delete values from the registry, the only way to do it, is by overwrite it with new data.&#x20;

#### Hive

Contains keys and values And the information about Hardware, user setting, software, system configuration.

#### Registry files

* Windows\system32\config : SAM, Security, System, Software, Default

#### Amcache

* Windows\appcompat\programs\Amcache.hve

#### User hive

Each user have a registry hive, which the specific user activity on the machine.

One of the most critical object to be examined.

* xp: c:\docments and settings\ {username}
* win 7-10: %userprofile%\appdata\local\microsoft\windows

#### Tools

* Registry explorer
* TZWorks cafae



## Event logs

![](https://remnote-user-data.s3.amazonaws.com/DCzzYyePgJqGXxe7LkgOqe\_y4z9KJBIZtaMdblCWN2CeaEQlPHqPtI34hqp0BL2Ub0hSGXQs-k\_ZB5sktuPm16yA4y261bq2F56acW2ct\_taUac\_BwS\_at4lwhdceYHp.png)

From vista and onward have logging has been enabled by default and started to be a key part of any windows forensic job. Centralized recording of information about software, hardware, OS function and security

There no limitiation to evtx file, but by default the size is set to 20Mb, once it reach the value it will start to overwrite historical events.

Default format for event viewer, it structured as XML format, it was change from vista because it reduced the memory cost of logging.

### Event types

* Error
  * Significant problem; loss of data or functionality, e.g. service fails to load
* Warning
  * Not significant but could indicate a future problem, e.g. low disk space.
* Information
  * Successful operation of application,driver or service
* Success audit
  * Audit event completed successfully
* Failure audit
  * Audit event did not complete sucessfully

### Type

#### Security

Most commonly reviewed log in forensics, can only be updated by the LSASS process. Records access control and security settings information.

Records access control and security settings information - Event based on audit and group policies

![](https://remnote-user-data.s3.amazonaws.com/PcQe9i\_trnHg7EfgF4N9aSZK6crmTiMdhcUOP6Z2k5HB99PJ6jhhn8NR-3XESJsrETzEjygsNAJOjUWgqd0MXf43A2mYt1SS7Cqzixowmq146ZFjEIGJ-pJSB18gk\_3K.png) ![](https://remnote-user-data.s3.amazonaws.com/TS97jbOpuhD\_AOEDuK9h9BDvE10dqCVGEIefhXhorjkbpyz9G8hNWAERFfRmurVuDwCTeNGE61iZaYobknDwL7EiKF6ycPAQIWP1UvbhQCG\_iBrmroAkQnZLvAwarZbh.png) ![](https://remnote-user-data.s3.amazonaws.com/cz5sKneMouKWqYCMui0dDADIt6OSRKSuD36z86ZR0krqVZY\_xBoDL0gn85TcCJcF9u4KgKMH1nsPwHySdOvOC0r\_u0TKyFYvS6jwNa8mDD1\_hKCw2Imfuuv1uaGuDUzc.png)

#### System

Contains event related to windows services, system components drivers resources, etc. e.g. service stop/start, system reboot.

#### Application

Software event unrelated to operating systeme.g. sql server fails to access a database

#### Custom

Custom application logs, examples server logs including directory service, DNS server and file replication service.







### Location

* XP : \windows\system32\config
* vista+ : \Windows\System32\winevt\Logs\\

### Tools

* Event log Explorer



## Memory

Highly volatile hardware using to stored information that the computer access frequently to increase the speed of read and write.

#### Hibernation

Introduced by Microsoft was an energy saving solution, where it will write the data in RAM to disk (hiberfil.sys). It was later restructured in win 10 to fast startup, which reduce the amount of time required for boot, this was done by using hibernation function, by freezing CPU and memory to the hiberfil.sys file.

#### Data

* Processes
* Open files, registry keys and devices
* Encryption keys and password
* Network connection
* Configuration parameters
* memory-only exploits / rootkit.

#### Analysis

![](https://remnote-user-data.s3.amazonaws.com/Os1EdlG6Jf2JIeIJPrTXTM7r4\_2zKYcIWxXiJTJ4GmyF2Gx97\_A28xhcyR3ETk6ikjmXX3jqKgC8xfrrS-fSE3oEmmAvkHt1T8\_LaBnBh2bzJ12yXcx3dhSsg\_ygTGeQ.png)

## Processes

![](https://remnote-user-data.s3.amazonaws.com/oVP\_A5b7scYID727yEFJVRu1ux0rKndvMymDisLIYDHHr9FsHIILDSDsX80NJQLzpkTYErVqYua3L0cWGzvxWGkJKCgmnSwYHiLJEEjwrATQchd7pJc4LqCBXvSCCkFi.png)

## Timestamps

The precious of the timestamp depends on the file system used.

![](https://remnote-user-data.s3.amazonaws.com/38vm07ZMSwFAdmLw3GzwBQTC57kuzkEp4zAdsEdengOuW1\_CoAY6ZpguxQi-w4QILc18n0ItPzgvR5PIvfIQ2ILrsAUn4zl95MfiAS8MT7fRGmYhMUr9pMpZZvq8MKs3.png) ![](https://remnote-user-data.s3.amazonaws.com/hGLcuRTKt4GV0eSEagcAV4E125e5dSd4d8QKF97uyOBiGeKI9gN8t-vR0xe3xwz\_Y\_Q3WGYBEKXPqygdEi2uGuUkeORcQ7wujCAicuf5C\_Q6bfnoI6FGuDnIMKmMbil6.png)

## Notes

If modified date is older than created date mean the file or folder have been copied. Does not count for files download from the internet.

* Key location
  * Hive files
    * windows\system32\config
    * %userprofile% - NTUser
  * Event files
    * \Windows\System32\winevt\Logs\\
    * svchost.exe should always be executed from service.
    * RPD - Security log event ID : 4778 & 4779\
      Will log the host machine name which initiated the connection
    * Kerbous
      * Security log
      * EventID
        * 4768 - TGT was granted (successful logon)
        * 4769 - Service ticket requested(access to server resource) : Once requested can to taken offline for cracking
        * 4771 - Pre-authentication failed (failed logon)
    * Network shares
      * Security log
      * Off by default
      * EventID
        * 5140 - Network share was accessed
        * 5145 - Shared object accessed
    * Services
      * EventID
        * 7035 - service sent a start or stop control
        * 7036 - service start or stop
        * 7040 - start type changed
        * 7045 - new service installed

## References

* [Windows Forensic Analysis | SANS Poster](https://www.sans.org/posters/windows-forensic-analysis/)
* [raw.githubusercontent.com/mark hallman/plaso filters/master/filter windows.txt](https://raw.githubusercontent.com/mark-hallman/plaso\_filters/master/filter\_windows.txt)