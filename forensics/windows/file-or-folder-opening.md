# File and folder opening

## Recent files

Registry key that will track the last files and folders opened.
Used to populate the information in the recent menu with the start menu. 

RecentDocs key will track the overall order of the last 150 files or folders opened. MRU list  is order by when the file was opened.\
Recentdocs is structured with subfolder of each file extension opened.
The last entry and modification time of the key will be the time and location the last file with the specific extension was opened.

.??? file extension

* This subkey stores the last files with a specific extension that was opened. MRU list will keep track of the order in which each file was opened. The last entry and modification time of this key will be the time when and location where the last file of a specific extension was opened. Can hold op to 10 records

Folder

* This subkey stores the last folders that were opened. The MRU list will keep track of the order in which each folder was opened. The last entry and modification time of this key will be the time and location of the last folder opened.

```
NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs 
```

## Shortcut files

.lnk are automatically created by windows in the recent folder when opening local or remote files or documents.
Each user have their own recent folder.
There is a limit of 149 files and folder LNK files in the recent directory.

Tool
* LeCMD


**Analysis**

There can not exists two lnk files of the same name in different location.
which is why the creation timestamp is the first time an file of that name was opened.
Modification date is the last time an file with that name was opened.

The information inside the lnk only points to the last file that was opened.

lnk files contains additional information inside them such as:
* External device information (Name,Type and serial number)
* Network share information
* Name of the system

Any non-executable will generate two lnk files.
* Target file
* parent folder of the target file


XP:

```
C:\%USERPROFILE%\Recent 
```

Win7+:

```
%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Recent\
```

```
%USERPROFILE%\AppData\Roaming\Microsoft\Office\Recent\
```


## Prefetch

Increases performance of a system by pre-loading code pages of commonly used applications. Cache Manager monitors all files and directories referenced for each application or process and maps them into a .pf file. Utilized to know an application was executed on a system.

* Limited to 128 files on XP and Win7
* Limited to 1024 files on Win8-10
* (exename)-(hash).pf

```
C:\Windows\Prefetch 
```



## Office recent files

MS office programs track recent files. It track the recent open files by that application

Reading location

* Position : The location of the cursor when was lasted closed.
* Datetime : last closed.

NTUSER : %Userprofile% or HKCU

* NTUSER.DAT\Software\Microsoft\Office\ {version} \ {program}
  * 14.0 = Office 2010
  * 11.0 = Office 2003
  * 12.0 = Office 2007
  * 10.0 = Office XP
* NTUSER.DAT\Software\Microsoft\Office\ {version} \ {program}\UserMRU\ {LiveID\_# or ADAL\_#} \ {FileMRU placeMRU}
  * 15.0 = Office 365 (2013)
  * 16.0 office 364 (2016)

Time

* Windows 64 hex value - big endian

## Office recent reading location

Stores information of the last cursor location for files opened by the user.
The key also stores the file path and the datetime for when the file was last closed. The datetime format is in 64-bit system time.


```
NTUSER.dat\SOFTWARE\Microsoft\Office\16.0\Word\Reading Locations\
```

## Shell bags

Records *folders* accessed by the user wether it on the local machine, network, and removable device. 
Record user folder and viewing preferences to Windows explorer.

Can be used to identify access time of folder and pinpoint deleted folder.

**Analysis**

The register structure mimic the tree structure of explorer.
Where bagMRU\0 is equal to my computer. And BagMru\0\ # is the drive letter by opening the register value data and viewing as ascii of you can identify the drive letter. And so it continues to be mapped.

By identifying the folder that have MRUListEX indicator you can assess when the directory was accessed.


* Devices
  * fat32 : sequence number null
  * NTFS : sequence number exists


Tools

* ShellbagExplorer
* SBEcmd
* sbag


**Explorer access:**

USRCLASS.dat location:
```
%userprofile%\AppData\Local\Microsoft\Windows\ 
```

```
USRCLASS.DAT\Local Settings\Software\Microsoft\Windows\Shell\Bags 
```
```
USRCLASS.DAT\Local Settings\Software\Microsoft\Windows\Shell\BagMRU
```

**Desktop access:**
```
NTUSER.DAT\Software\Microsoft\Windows\Shell\BagMRU
```

```
NTUSER.DAT\Software\Microsoft\Windows\Shell\Bags
```



## IE History

IE history will also keep track of file opening.

```
%appdata%\local\microsoft\windows\webcache\WebCacheV*.dat
```

Tools

* NirSoft BrowsingHistoryView

## Open/save MRU

Tracks file that have been opened and saved using the windows shell dialog box.
It tracks by file extension.

* XP
  * NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSaveMRU
* Win7/8/10
  * NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePIDlMRU




## Jump List

With windows 7 Microsoft introduced the jump list. Which track the recent files opened by that application.
The files inside the AutomaticDestinations folder are databases of shell items. Because it an database file deleting the entries from the database is difficult.\
Each entries or stream within the database is a lnk file, if exported can be analysis using the same tool for lnk shortcut files.


The naming convention of jump list files is {AppID}.AutomaticDestinations-ms.\
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

Can be used to track remote desktop usage and recent destinations.


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
