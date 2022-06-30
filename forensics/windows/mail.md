# Mail

### Email attachment

Where outlook attachment are stored. Outlook uses a secure temp folder to open attachments. Outlook 07+ attachments remain only if the message or outlook is closed before the attachment, or in the event of an application crash.

* Outlook
  * userprofile%\local\microsoft\windows\Inetcache\content.outlook
  * %USERPROFILE%\AppData\Local\Microsoft\temporary internet files\content.outlook

### Archives

Encryption or obfuscation is enabled by default, archive can be up to 50 GB. File extension .pst

* outlook 2010 or earlier
  * %userprofile%\appdata\local\microsoft\outlook
* Archive type
  * HKCU\software\microsoft\windowsNT\CurrentVersion\Windows messaging subsystem\profiles\outlook

### offline folder files

Allow for offline mail access also called "cached exchage mode"

* File extension .ost
* last 12 month of mail by default
* max 50gb by default

Outlook

* XP: %USERPROFILE%\Local Settings\ApplicationData\Microsoft\Outlook
* win7/8/10: C:\Users\AVHN\AppData\Local\Microsoft\Outlook

### Export mail in exchange

Automatically includes recoverable items

```
new-mailboxExportREquest -Mailbox {name} -filepath xxx\xxx\xxx.pst
```

```
New-compliancesearch
```
