---
description: Windows location for finding system information
---

# System information

### OS version

Determine the window version, service pack.

```
SOFTWARE\Microsoft\Windows NT\CurrentVersion
```

Time in unix seconds

### Computer name

```
SYSTEM\CurrentControlSet\Control\Computername\Computername
```

### Time zone information

Identify system time zone, it is a critical important because internal log files and date/timestamp will be based on the system time zone

```
SYSTEM\CurrentControlSet\Coontrol\TimeZoneInformation
```

### NTFS last access time no/off

Disabled means the last access timestamp will not be recorded in the NTFS file system\
It means that you will not be able to see when data was last accessed by the system. - If value = 0x1 then it disable



```
SYSTEM\CurrentControlSet\Control\Filesystem
```

### Network interfaces

Network interface cards, list network interfaces of the computer and allows you to tie machine to network activity.

```
SYSTEM\CurrentControlSet\Services\TcpIPp\Parameters\Interfaces
```

### Shutdown

When the system was last shutdown

Timestamp in hex encoded windows 64-bit time

DCode can be used to convert the time

```
SYSTEM\CurrentControlSet\Control\Windows
```

### Volume info

```
SYSTEM\mounteddevices  
```

### System Resource usage monitor (SCUM)

Records 30 to 60 days of historical system performance, with data being saved every hour. Applications run, user account responsible for each, and application and bytes sent/received per application per hour. Use tool such as srum\_dump.exe to cross correlate the data between the registry keys and the SRUM ESE Database.

Tools\
Nirsoft\
Scrum-dump\
ScrumMonkey

```
HKLM\SOFTWARE\Microsoft\WindowsNT\CurrentVersion\SRUM\Extensions {d10ca2fe-6fcf4f6d-848e-b2e99266fa89}
Application Resource Usage Provider C:\Windows\System32\SRU\SRUDB.dat
```

### Installed software&#x20;

```
SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall
```
