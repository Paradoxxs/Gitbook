# Windows

### Acquisition

Steps takes during windows acqusition, triage image might be skipped it all depends on the company policy.

### Create memory image

#### Live

* FTK imager
* Magnet forensics RAMCapture
* Belkasoft Live RAM capturer
* DumpIT

#### Deadbox

* Hibernation file
  * %SystemDrive%/hiberfil.sys
* Page file
  * %systemDrive%/pagefile.sys
* Memory dump
  * %windir%/memory.dmp

#### Check for disk encryption

Ensuring the computer and any attached disk are not encrypted, if they are now is the time to extract data from the different sources.

* Tool
  * Magnet forensics encryption disk detector
  * Live logical image evaluation

### Create quick triage image

Because of the increasing the size of disk, the process of doing full disk imaging have become too slow. Another reason for during triage image is that you only require an minimal amount of data to get most of the context on the computer.

#### Tools

* CYLR - using config file
* FTK imager - Create custom content image

#### Key Artifacts

* Registry hives and backups
  * Transaction logs
* Volume shadow copy
* LNK files
* Jump lists
* Prefetch
* Event logs and PnP logs
* Browser data
* Recycle bin
* Master file table
* NTFS log files and journal log
* Pagefile and Hibernation files

### Begin analysis of triage image

Here we analysis the triage image and identify if we need additional data for the case, if not we go to the next stage of imaging the entire drive.

### Image entire hard drive

The process of imaging the entire drive of the device.&#x20;

* FTK imager - Create disk image
