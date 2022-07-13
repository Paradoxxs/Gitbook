# File knowledge

### Master file table (MFT)

NFTS hold a MFT of all the files that currently on the system, requires a physical image of the drive.

Tool\
MFT explorer\
MFTEcmd

```cmd
[root]\$MFT
```

### Thumbcache & thumbs.db

Thumbnails of pictures, office document and folder exist in a database called thumbcache. where each user have their own database based on thumbnail sized.\
thumbcache is created automatically in folders accessed via explorer which contains pictures.

thumbs.db is database of pictures in folder and stores a copy of the thumbnail even if the pictures were deleted.



tool\
thumbsdb viewer\
thumbscache viewer

thumbs.db:

```cmd
%Userprofile%\AppData\Local\Microsoft\Windows\Explorer
```

### Shimcache

Windows application compatibility database is used by Windows to identify possible application compatibility challenges of execution.
Any executable run on the Windows system could be found  in this key. You can use this key to identify systems that  specific malware was executed on. In addition, based on the  interpretation of the time-based data you might be able to  determine the last time of execution or activity on the system.

- Windows 10+ shimcache can no longer be used to determine last execute time
- Windows XP contains at most 96 entries  - LastUpdateTime is updated when the files are executed
- Windows 7+ contains at most 1,024 entries  - LastUpdateTime does not exist on Win7 systems.
- new content, moving or renaming the file will make a new Shimcache
- It will tracks the file last modification date, file path and if it was executed
- InsertFlag = true (executed)

Timestamp is when the file was last modified

````cmd
SYSTEM\\CurrentControlSet\\Control\\Session Manager\\AppCompatCache
````

### NTFS Alternate data stream zone identifier (ADS) Zone identifier

Tell the source of the file (NoZone = -1 MyComputer = 0 Intranet= 1 Trusted= 2 Internet= 3 Untrusted= 4)

````powershell
Get-ChildItem -Recurse | Get-Content -Stream Zone.Identifier -ErrorAction SilentlyContinue
````