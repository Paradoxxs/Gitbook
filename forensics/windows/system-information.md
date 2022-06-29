---
description: Windows location for finding system information
---

# System information

#### OS version

```
SOFTWARE\Microsoft\Windows NT\CurrentVersion
```

Time in unix seconds

#### Computer name

```
SYSTEM\CurrentControlSet\Control\Computername\Computername
```

#### Time zone information

```
SYSTEM\CurrentControlSet\Coontrol\TimeZoneInformation
```

#### NTFS last access time no/off

```
SYSTEM\CurrentControlSet\Control\Filesystem
```

#### Network interfaces

```
SYSTEM\CurrentControlSet\Services\TcpIPp\Parameters\Interfaces
```

#### Shutdown

Timestamp in hex encoded windows 64-bit time

```
SYSTEM\CurrentControlSet\Control\Windows
```

#### Installed software&#x20;

```
SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall
```
