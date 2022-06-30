# Program & file execution



### UserAssist

List GUI-based program executed by specific user. Uses GUID folder structured.

All vaues are ROT-13 encoded

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
  * D65231Bo : ssystemX86
  * B4BFCC3A : Desktop
  * FDD39AD0 : documents
  * 374DE290 : Downloads
  * 0762D272 : Userprofiles

Time

* Last run time (UTC) Tool
* Nirsoft userassistview

```
NTUSER.DAT\Software\Microsoft\Windows\Currentversion\Explorer\UserAssist\ {GUID}\Count  
```

### Win 10 timeline

Records of recently used application and files in a timeline accessible via "win+tab" key, the data is recorded in sqLite database.

```
C:\Users\AppData\Local\ConnectedDevices Platform\ActivitiesCache.db  
```

### BAM/DAM

Windows background activity moderator (BAM). Desktop activity moderator (DAM).

Provides full path of the executed files that were run on the systems and last execution datetime

```
SYSTEM\CurrentControlSet\Services\bam\UserSettings\{SID}  
```

```
SYSTEM\CurrentControlSet\Services\dam\UserSettings\{SID}
```

### Shimcache - application compatibility

Windows application compatibility database is used by Windows to identify possible application compatibility challenges of execution.

Any executable run on the Windows system could be found in this key. You can use this key to identify systems that specific malware was executed on. In addition, based on the interpretation of the time-based data you might be able to determine the last time of execution or activity on the system.

* Windows XP contains at most 96 entries - LastUpdateTime is updated when the files are executed
* Win 7+ contains at most 1,024 entries - LastUpdateTime does not exist on the systems, meaing it can no longer be used to determine last execute time

Note

* new content, moving or renaming the file will make a new Shimcache
* It will tracks the file last modification date, file path and if it was executed
* InsertFlag = true (executed)

Time

* Timestamp is when the file was last modified

Tool

* AppCompatCacheParser

XP:

```
HKLM\SYSTEM\CurrentControlSet\Control\SessionManager\AppCompatibility
```

Win7/8/10:

```
HKLM\SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatCache  
```

### amcache.hve

ProgramDataUpdater (a task associated with the Application Experience Service) uses the registry file Amcache.hve to store data during process creation. Amcache.hve – Keys = Amcache.hve\Root\File{Volume GUID}#######

Entry for every executable run, full path information, Files $StandardInfo Last Modification Time, and Disk volume the executable was run from

* First Run Time = Last Modification Time of Key
* SHA1 hash of executable also contained in the key.
* Value name are in hex from 0 to 17, 100 and 101 corresponding to a name ![](https://remnote-user-data.s3.amazonaws.com/BJmFS6dKo-ItyK1qQCSxnJQcW6tqIHTAGEwI02jHF7A8sY763OSmPQGXPTEDzW98xQ446FJx6MtlxIvCm6mAOhdYMHUy3CCuq1ixOo3pvdxqzV6HGUdIqF9wVhcyiQ4L.png)

time

* First run time = last modification time of key

Tool

* amcacheParser

```
C:\Windows\AppCompat\Programs\Amcache.hve 
```

Key:

```
amcache.hve\Root\File\{Volume GUID}\#
```

### System resource usage monitor (SRUM)

Records 30 to 60 days of historical system performance. Applications run, user account responsible for each, and application and bytes sent/received per application per hour.

Use tool such as srum\_dump.exe to cross correlate the data between the registry keys and the SRUM ESE Database.

Tools

* Nirsoft
* Scrum-dump
* scrumMonkey

```
C:\Windows\System32\SRU\SRUDB.dat
```

### Jump List

Analysis

* Every steam is an shell-item, steam are separate LNK files

First time of execution of application.

* Creation Time = First time item added to the AppID file.

Last time of execution of application w/file open.

* Modification Time = Last time item added to the AppID file.

MRU

* Order by how recent the file was open
* List of Jump List IDs -> [https://dfir.to/EZJumpList](https://dfir.to/EZJumpList)

Tools

* AutomaticDestination : MiTec Structured storage viewer
  * Export stream to save lnk file (right-click on stream)
* JLECmd - dump out all lnk files.
* jmp - TZWorks
  * Parse both automatic and custom files

```
C:\%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations
```

### Last-visited MRU

Tracks the specific executable used by an application to open the files documented in the OpenSaveMRU key. In addition, each value also tracks the directory location for the last file that was accessed by that application. Example: Notepad.exe was last run using the C:%USERPROFILE%\Desktop folder

XP:

```
NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedMRU
```

Win7/8/10:

```
NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\ LastVisitedPidlMRU
```

### RUN box execution

Commands typed in RUN box.

```
NTuser.dat\software\microsoft\windows\CurrentVersion\Explorer\RunMRU
```

### RecentApp

Track execution of GUI based application and recent file opened by that application. Can also be used to track usage of remote desktop and the destination.

Key

* RecentApp GUID
  * APPID = name of application
  * LastaccessTIme = last execution time in UTC
  * LunchCount = count of execution
  * RecentItem GUID (the file the application open)
    * path of file or destination
    * LastAccessTime

Time

* LastaccessTIme = last execution time in UTC

```
ntuser.dat\Software\microsoft\windows\CurrentVersion\Search\RecentApps
```

### Prefetch

increasing the performance of the system by pre-loading code pages. The cache manager monitors all files and directories and maps them into a .pf file, which is utilized to show application execution.

It disables on system with SSD, otherwise enabled by default, on win10+ are the files are compressed.

Analysis

* win8/10 store the last 8 times executed embedded in each .pf file
* date modified - last executed
* date created - first executed
* Each .pf will include last time of execution, number of times run, and device and file handles used by the program

Limitation

* vista and win7 - max 128 files
* win8/10 - max 1024 files

Tools

* PEcmd - prefetch explorer cmd
* pf - by TZworks.net

```
Window\prefetch\layout.ini 
```

### RecentDocs

Registry Key that will track the last files and folders opened and is used to populate data in “Recent” menus of the Start menu, It the MRUlist that is used to create the order in which files are opened.

```
Software\microsoft\windows\currentverion\explorer\recentdocs
```

### LastVisitedMRU

Tracks application used to open files in OpenSavMRU and the file path. Track the specific executable used by an application to open the files documented in OpenSaveMRU key.

```
NTUser.dat\software\Microsoft\windows\currentVersion\Explorer\ComDlg32\LastVisitedPidlMRU
```
