# Network activity

### Network history

History of connected network.\
Identify intranets and network that the computer have been connected to.

* Allow you to determine the intranet name, but you can also determine the last time the network was connected to it based on the last write time of the key.
* This will also list any networks that have been connected to via a VPN.
* MAC Address of SSID for Gateway could be physically triangulated.
* Identify SSID
* Gateway MAC address
* Domain names

Win7+:

```
SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Nla\Cache
```

```
SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures\Managed
```

```
SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures\Unmanaged
```

###

### WLAN event log

Determine what wireless network system associated with and identify network characteristics to find location.

Event IDs

* 11000 – Wireless network association started
* 8001 – Successful connection to a wireless network
* 8002 – Failed connection to wireless network
* 8003 – Disconnect from wireless network
* 6100 – Network diagnostics (System log)

```
Windows/system32/config/Microsoft-Windows-WLAN-AutoConfig Operational.evtx
```

### RDP usage

Track remote desktop protocol logons to machines.\
another benefit of RDP log is that it will log the origin hostname of the connection.



Event id: \
4778 - Session connected / reconnected\
4779 - Session disconnected

```
%system root%\system32\winevt\logs\security.evtx
```



### Shares and offline caching

List open network shares on the computer, and flags and configuration settings. Look for and identify possible offline caching.\
Info about the type of shares and the local path, if no shares show up then the user have not created any new shares

#### Fields

CSCFlags : caching setting

* CSCFlags : caching setting
  * 0 - default option, user specify the files that is cached
  * 16 - Automatic document caching "Files and program that the user open are automatically cached
  * 32 - Automatic program caching with optimized for performance
  * 48 - Caching disabled
  * 2048 default win7+ setting Path : folder path Permissions : how share was created
* Remark : user added comment
* type : share type.
  * 0 - Disk drive or folder
  * 1- Printer
  * 2 - Device
  * 3- IPC
  * 2147483648 - Admin

```
System\CurrentControlSet\Service\Lanmanserver\share\
```

### Network shares

Event id:\
5140-5145

```
Windows\system32\winevt\logs\security
```

### Network profiles key - first and last connected

Identify the type of network the computer was connected to, will store the SSID of previous wireless network.\
Time is in computer localtime.

```
SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Profiles
```

### IP address

```
SYSTEM\currentcontrolset\services\tcpip\parameters\interfaces\{GUID}
```




