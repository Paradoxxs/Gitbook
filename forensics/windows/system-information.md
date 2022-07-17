---
description: Windows location for finding system information
---

# System information

### OS version

Stores the window version and service pack, and the installation date.

```
SOFTWARE\Microsoft\Windows NT\CurrentVersion
```

Time in unix seconds

### Computer name

The hostname of the computer.

```
SYSTEM\CurrentControlSet\Control\Computername\Computername
```

### Time zone information

Identify the system time zone. It is a critical important because some log files and register key are set system time zone, and the other in UTC.
Making it critical important to know the difference between system time and UTC.

Very usefull when you need to correlate event across multiple devices you need to make sure that you view the time in the same format and time zone across all devices. 


```
SYSTEM\CurrentControlSet\Coontrol\TimeZoneInformation
```

### NTFS last access time no/off

Disabled means the last access timestamp will not be recorded in the NTFS file system\
It means that you will not be able to see when data was last accessed by the system.
If value = 0x1 then it disable



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

### Default apps

The default application of the machine.\
Very useful to identify the web browser that is used.

````
SOFTWARE\Microsoft\Windows\CurrentVersion
````

## Network interfaces

List network interfaces of the machine. 
Allow you to determine if the machine have an static IP or uses DHCP.
Stores the DHCP server address and the default gateway foreach network interface. 

It does not stores all network interfaces when windows decided to record an network interface is not known yet.
And the first and last network connection, the datetime is stored in localtime. The format is in windows system 128-bit format.

It also list any networks that have been connected to via VPN 

**Analysis**

You can physical locate an person by using the SSID of wifi connection. Using [wigle](https://wigle.net/) to Geolocate the wifi signel. 
```
SYSTEM\CurrentCOntrolSet\Services\Tcpip\Parameters\Interfaces
```

## Historical network 

Track the networks the computer  have been connected, both wired and wireless. 

Records the domain/intranet name, the SSID and the gateway mac address.

```
SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures\unmanged
```

```
SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures\manged
```

```
SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Nla\Cache
```



## Shares and offline caching

Records of open network share on the local system. And the flags and configuration settings.


|fields|Description|
|---|---|
|CSCFlags|Caching setting
|MaxUser|max user|
|Path|Folder path|
|Permissions| How the share was created|
Remark|User added comment|
Type| Share type


```
SYSTEM\CurrentControlSet\Services\lanmanserver\Share\
```
