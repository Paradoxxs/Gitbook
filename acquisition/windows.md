# Windows

### Acquisition

Steps takes during windows acqusition, triage image might be skipped it all depends on the company policy.

### Create memory image

Live

* FTK imager
* Magnet forensics RAMCapture
* Belkasoft Live RAM capturer
* DumpIT

Deadbox

* Hibernation file
  * %SystemDrive%/hiberfil.sys
* Page file
  * %systemDrive%/pagefile.sys
* Memory dump
  * %windir%/memory.dmp

#### Check for disk encryption

* Tool
  * Magnet forensics encryption disk detector
  * Live logical image evaluation

### Create quick triage image

Because of the increasing the size of disk, the process of during full disk imaging have become too slow.

Tools

* CYLR - using config file
* FTK imager - Create custom content image

Key Artifacts

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

### Image entire hard drive

* FTK imager - Create disk image
