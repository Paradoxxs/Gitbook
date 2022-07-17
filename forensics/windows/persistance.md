---
description: Location of where software / malware can persists
---

# Persistance

Places to look for programs that start automatically at system boot or user logon

## Auto start of programs

```
%userprofile%\AppData\Roaming\Microsoft\Windows\Start menu\Programs\Startup
```

### User startup registry 

```
NTUSER.dat\Software\Microsoft\Windows\CurrentVersion\Run
NTUSER.dat\Software\Microsoft\Windows\CurrentVersion\RunOnce
```

### Startup registry Explorer

```
SOTFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer
```

### Startup registry userinit

```
SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Userinit
```

## Scheduled task

Event ID:\
Security 4698\
Task scheduler: 106, 141 and 200

```
Windows\System32\winevt\logs\security
Windows\System32\winevt\logs\task scheduler
```

## Boot log

```
Windows\System32\WDI\LogFiles\BootCKCL.etl
```

## Service eventlog

EventID\
System: 7034-7036, 7040, 7045\
Security: 4697



### Service events

Analyze logs for suspicious service running&#x20;

Event id:

System
* 7034 – Service crashed unexpectedly
* 7035 – Service sent a Start/Stop control
* 7036 – Service started or stopped
* 7040 – Start type changed (Boot | On Request | Disabled)
* 7045 – A service was installed on the system (Win2008R2+)

Security
* 4697 – A service was installed on the system 


```
Windows\System32\winevt\logs\System.evtx
Windows\System32\winevt\logs\Security.evtx
```


## Service

Service with 0x02 flag start at boot

```
SYSTEM\CurrentControlSet\Services
```
