---
description: Commands executed by the system or user
---

# Command

#### Powershell history

History of powershell executed by the user

```
%appdata%\roaming\Microsoft\Windows\Powershell\PSReadLine\consoleHost_History.txt
```

#### WMI

```
Get-WMIObject -Namespace root\Subscription -Class __EventFilter 
Get-WMIObject -Namespace root\Subscription -Class __EventConsumer 
Get-WMIObject -Namespace root\Subscription -Class __FliterToConsumerBinding 
```

#### WMI database

Objects.data = object managed by WMI

Index.btr = binary tree index, index files imported into objects.data

Mapping\[1-3].map = correlates data in objects.data and index.btr

Tool:\
PyWMIPersistanceFinder.py

```
%systemroot%\system32\wbem\repository
```

#### Command line event log

Event id\
Security: 4688

Powershell\operational: 4103 - 4106

```
Windows\System32\winevt\logs\Security
Windows\System32\winevt\logs\Powershell\operational
```

#### WMI event log

Event id\
WMI-activity/operational 5847 - 5861

```
Windows\System32\winevt\logs\Security
Windows\System32\winevt\logs\Powershell\operational
```

#### Last command executed

```
NTUSER.dat\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU
```
