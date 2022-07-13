# Account usage

### SAM

List local account events

* Last login
* Last failed login
* Logon count
* Password policy
* Password change
* Password hit

Time is in UTC

Tool:\
SamInsider

```
SAM\Domain\account\Users
```

### Service events

Analyze logs for suspicious service running&#x20;

Event id:

* 7034 – Service crashed unexpectedly
* 7035 – Service sent a Start/Stop control
* 7036 – Service started or stopped
* 7040 – Start type changed (Boot | On Request | Disabled)
* 7045 – A service was installed on the system (Win2008R2+)
* 4697 – A service was installed on the system (from Security log)

```
windows\system32\winevt\logs\system.evtx
```

### Logon types

Give information about the nature of the account authentication

Event id: 4624

* 2 Logon via console
* 3 Network Logon
* 4 Batch Logon
* 5 Windows Service Logon
* 7 Credentials used to unlock screen
* 8 Network logon sending credentials (cleartext)
* 9 Different credentials used than logged on user
* 10 Remote interactive logon (RDP)
* 11 Cached credentials used to logon
* 12 Cached remote interactive (similar to Type 10)
* 13 Cached unlock (similar to Type 7)

```
windows\system32\winevt\logs\Security.evtx
```

### Authentication events

Authentication mechanisms

* 4776: Successful/Failed account authentication Event ID Codes (Kerberos protocol)
* 4768: Ticket Granting Ticket was granted (successful logon)
* 4769: Service Ticket requested (access to server resource)
* 4771: Pre-authentication failed (failed logon)

```
Window\System32\winevt\logs\Security.evtx
```

### Success & failed logon events

Determine which account have been used for authentication attempt

Event Id:

* 4624 – Successful Logon
* 4625 – Failed Logon
* 4634 | 4647 – Successful Logoff
* 4648 – Logon using explicit credentials (Runas)
* 4672 – Account logon with superuser rights (Administrator)
* 4720 – An account was created

```
Window\System32\winevt\logs\Security.evtx
```

### WordWheelQuery

Stores user search history for explorer and start menu

````
NTUSER.DAT\\Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\WordWheelQuery
````

### Typed path

Stores the typed path in the explorer addressbar

````
NTUSER.DAT\\software\\microsoft\\windows\\CurrentVersion\\Explorer\\TypedPaths
````

