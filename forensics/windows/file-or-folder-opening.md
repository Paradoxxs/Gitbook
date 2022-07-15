# File and folder opening

## Recent files

Registry key that will track the last files and folders opened.

RecentDocs

* Overall key will track the overall order of the last 150 files or folders opened. MRU list will keep track of the temporal order in which each file/folder was opened. The last entry and modification time of this key will be the time and location the last file of a specific extension was opened.

.???

* This subkey stores the last files with a specific extension that was opened. MRU list will keep track of the temporal order in which each file was opened. The last entry and modification time of this key will be the time when and location where the last file of a specific extension was opened. Can hold op to 10 records

Folder

* This subkey stores the last folders that were opened. MRU list will keep track of the temporal order in which each folder was opened. The last entry and modification time of this key will be the time and location of the last folder opened.

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

Stores the information of the last reading location for the recent file opened by the user.

Timestamp

* datetime in 64-bit system time, stores when the file was last closed

```
NTUSER.dat\SOFTWARE\Microsoft\Office\16.0\Word\Reading Locations\
```

## Shell bags

Which folders were accessed by the user on the local machine, network, and removable device. User-specific Windows folder and viewing preferences to Windows explorer.

Analysis

* Key items
  * MRUListEX
    * Directory was accessed at that time
  * Devices
    * fat32 : sequence number null
    * NTFS : sequence number exists
* Mimic the tree structure of the explorer

Tools

* ShellbagExplorer
* SBEcmd
* sbag

```
%userprofile%\AppData\Local\Microsoft\Windows\
```

```
USRCLASS.DAT\Local Settings\Software\Microsoft\Windows\Shell\Bags 
```

```
USRCLASS.DAT\Local Settings\Software\Microsoft\Windows\Shell\BagMRU
```

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

Tracks file that have been opened or saved within a windows shell, will be tracked by file extension.

* XP
  * NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSaveMRU
* Win7/8/10
  * NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePIDlMRU
