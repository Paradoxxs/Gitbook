---
description: Location of where software / malware can persists
---

# Persistance

Places to look for programs that start automatically at system boot or user logon

#### Startup folder

```
%userprofile%\AppData\Roaming\Microsoft\Windows\Start menu\Programs\Startup
```



#### Startup registry runonce

```
NTUSER.dat\Software\Microsoft\Windows\CurrentVersion\Run
NTUSER.dat\Software\Microsoft\Windows\CurrentVersion\RunOnce
```

#### Startup registry Explorer

```
SOTFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer
```

#### Startup registry userinit

```
SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Userinit
```

#### Scheduled task

Event ID:\
Security 4698\
Task scheduler: 106, 141 and 200

```
Windows\System32\winevt\logs\security
Windows\System32\winevt\logs\task scheduler
```

#### Boot log

```
Windows\System32\WDI\LogFiles\BootCKCL.etl
```

#### Service eventlog

EventID\
System: 7034-7036, 7040, 7045\
Security: 4697

```
Windows\System32\winevt\logs\System
Windows\System32\winevt\logs\Security
```

#### Service

Service with 0x02 flag start at boot

```
SYSTEM\CurrentControlSet\Services
```
