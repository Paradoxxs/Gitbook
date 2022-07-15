# Program execution



## UserAssist

List GUI-based program executed by the specific user and the run count. 
Organized by application GUID.

All values are ROT-13 encoded.

Last run time  is in UTC

* XP & vista
  * 5e6ab780.. ⇒ internet toolbar
  * 75048700.. ⇒ Active Desktop
* Win7 and up
  * CEBFF5CD ⇒ executable file
  * F4E57C4B ⇒ Shortcut file execution
* Other
  * 6D809377 : ProgramFilesX64
  * 7C5A40EF : ProgramFIlesX86
  * 1AC14E77 : system
  * D65231Bo : systemX86
  * B4BFCC3A : Desktop
  * FDD39AD0 : documents
  * 374DE290 : Downloads
  * 0762D272 : Userprofiles

Tool
* 
* Nirsoft userassistview

```
NTUSER.DAT\Software\Microsoft\Windows\Currentversion\Explorer\UserAssist\ {GUID}\Count  
```

## Win 10 timeline

Records of recently used application and files in a timeline accessible via "win+tab" key, the data is recorded in sqLite database.

```
C:\Users\AppData\Local\ConnectedDevicesPlatform\{GUID}\ActivitiesCache.db  
```

## BAM/DAM

Windows background activity moderator (BAM) & Desktop activity moderator (DAM).

Provides full path of the executed files that were run on the systems and last execution datetime

```
SYSTEM\CurrentControlSet\Services\bam\UserSettings\{SID}  
```

```
SYSTEM\CurrentControlSet\Services\dam\UserSettings\{SID}
```

## Shimcache - application compatibility

Windows application compatibility database is used by Windows to identify possible application compatibility challenges of execution.
The timestamp is when the file was last modified

Any executable ran on the Windows system could be found in this key. You can use this key to identify what systems the specific malware was executed on. 
Addition, based on the interpretation of the time-based data you might be able to determine the last time of execution or activity on the system.

* Windows XP contains at most 96 entries - LastUpdateTime is updated when the files are executed
* Win 7+ contains at most 1,024 entries - LastUpdateTime is removed from the entries, meaning it can no longer be used to determine last execute time

**Analysis**

* new content, moving or renaming of the file will make a new Shimcache.
* It will tracks the file last modification date, file path and if it was executed
* InsertFlag = true (executed)


Tool

* AppCompatCacheParser

XP:

```
HKLM\SYSTEM\CurrentControlSet\Control\SessionManager\AppCompatibility
```

Win7+:

```
HKLM\SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatCache  
```

## amcache.hve

ProgramDataUpdater a task associated with the Application Experience Service. Uses the registry file Amcache.hve to store data during process creation. 

Amcache.hve – Keys = Amcache.hve\Root\File{Volume GUID}#####

Entry for every executable run, full path information, Files $StandardInfo Last Modification Time, and Disk volume the executable was run from

* First Run Time = Last Modification Time of Key
* SHA1 hash of executable also contained in the key.
* Value name are in hex from 0 to 17, 100 and 101 corresponding to a name ![](https://remnote-user-data.s3.amazonaws.com/BJmFS6dKo-ItyK1qQCSxnJQcW6tqIHTAGEwI02jHF7A8sY763OSmPQGXPTEDzW98xQ446FJx6MtlxIvCm6mAOhdYMHUy3CCuq1ixOo3pvdxqzV6HGUdIqF9wVhcyiQ4L.png)


Tool
* amcacheParser

amcache.hve location:
```
C:\Windows\AppCompat\Programs\Amcache.hve 
```

Key:

```
amcache.hve\Root\File\{Volume GUID}\#
```

## System resource usage monitor (SRUM)

Records 30 to 60 days of historical system performance. Applications run, user account responsible for each, and application and bytes sent/received per application per hour.

Use tool such as srum\_dump.exe to cross correlate the data between the registry keys and the SRUM ESE Database.

Tools

* Nirsoft
* Scrum-dump
* scrumMonkey

```
C:\Windows\System32\SRU\SRUDB.dat
```

## Jump List

With windows 7 Microsoft introduced the jump list. Which track the recent files opened by that application.
The files inside the AutomaticDestinations folder are databases of shell items. Because it an database file deleting the entries from the database is difficult.
The naming convention of jump list files is {AppID}.AutomaticDestinations-ms.

Where each version of an application have it own app id. [EZJumpList](https://dfir.to/EZJumpList) host a list of the common application and version and its corresponding app id.

There are also custom destinations which are an optional feature developer can enable for their application.
What it records is up to the developer. They follow the same naming convention as AutomaticDestination with {AppID}.CustomDestinations-ms.
e.g. Firefox custom entries tracks new tabs, opening of browser, if the user was private browsing, sites.

**Analysis**

The larger the file is the more frequent the application is used.

* Every steam is an shell-item, steam are separate LNK files

First time of execution of application.

* Creation Time = First time item added to the AppID file.

Last time of execution of application w/file open.

* Modification Time = Last time item added to the AppID file.




Tools

* AutomaticDestination : MiTec Structured storage viewer
  * Export stream to save lnk file (right-click on stream)
* JLECmd - dump out all lnk files.
* jmp - TZWorks
  * Parse both automatic and custom files


AutomaticDestination:
```
%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations
```

CustomDestinations:
```
%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Recent\CustomDestinations
```

## Last-visited MRU

Tracks the specific executable used by an application to open the files documented in the OpenSaveMRU key. In addition, each value also tracks the directory location for the last file that was accessed by that application. Example: Notepad.exe was last run using the C:%USERPROFILE%\Desktop folder

XP:

```
NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedMRU
```

Win7/8/10:

```
NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\ LastVisitedPidlMRU
```

## RUN box execution

Execution of program through the RUN box (Win+R).
Is order by when command was executed.

```
NTuser.dat\software\microsoft\windows\CurrentVersion\Explorer\RunMRU
```

## RecentApp

Track user execution of GUI based application and files recently opened by that application.
Can also be used to track usage of remote desktop and the destination.

Keys:
RecentApp GUID
* APPID = name of application
* LastaccessTIme = last execution time in UTC
* LunchCount = count of execution

RecentItem GUID (the file the application open)
* path of file or destination
* LastAccessTime





```
ntuser.dat\Software\microsoft\windows\CurrentVersion\Search\RecentApps
```
Recent item key:
```
ntuser.dat\Software\microsoft\windows\CurrentVersion\Search\RecentApps\{APP GUID}\RecentItems
```

## Prefetch

Prefetch increases the performance of the system by pre-loading code pages. The cache manager monitors all files and directories and maps them into a .pf file, which is utilized to show application execution.

In the begging of win7 it was disables on system with SSD, buy was later enable again because of the performance boot, on win10+ are the files are compressed.

Analysis

* win8/10 store the last 8 times executed embedded in each .pf file
* date modified - last executed
* date created - first executed
* Each .pf will include last time of execution, number of times run, and device and file handles used by the program

Limitation:
* vista and win7: max 128 files
* win8+: max 1024 files

Tools

* PEcmd - prefetch explorer cmd
* pf - by TZworks.net

```
Window\prefetch\layout.ini 
```

## RecentDocs

Registry Key that will track the last files and folders opened and is used to populate data in “Recent” menus of the Start menu, It the MRUlist that is used to create the order in which files are opened.

```
Software\microsoft\windows\currentverion\explorer\recentdocs
```

## LastVisitedMRU

Tracks application used to open files in OpenSavMRU and the file path. Track the specific executable used by an application to open the files documented in OpenSaveMRU key.

```
NTUser.dat\software\Microsoft\windows\currentVersion\Explorer\ComDlg32\LastVisitedPidlMRU
```
