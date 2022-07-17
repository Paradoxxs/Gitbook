# Account 

Information about account and authentication events.

### SAM

List local account events
* Last login
* Last failed login
* Logon count
* Password policy
* Password change
* Password hit

**Analysis**

If you see a user with NT-hash starting with *31DCFE0D16AE931B7* the user have blank password.
Stores information on Account creation time, last logon time and last password change, all are stored in UTC.

If the invalid login count is at 0 it could indicate that it an Microsoft account.

Tool
* SamInsider

```
SAM\Domain\account\Users
```



### Logon event types

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


## Dead box password cracking 

Having both SAM and SYSTEM hive files you can export account hashes by using Mimikatz. 

Dump NT hashes
```
lsadump::sam /system:system.hive /sam:sm.hive
```

Password cracking using hashcat
```
hashcat -m 1000 -a 3 hash.txt
```