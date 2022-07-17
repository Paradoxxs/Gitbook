# User activity

### Search history

User keyword searched for in the start menu bar on win7+ 
The keywords are added in unicode and listed in a MRUlist.

With Win8+ the search bar gets added to the explorer menu.


```
ntuser.dat\software\microsoft\windows\CurrentVersion\Explorer\wordwheelQuery
```

### Typed path

The paths typed into the explorer address bar.
Windows uses it to perm auto complete.

```
ntuser.dat\software\microsoft\windows\CurrentVersion\Explorer\TypedPaths
```

## Windows common dialog box

The dialog box that opens when using the function *open* or *save as* with an application and the windows dialog box opens.

### OpenSaveMRU 

*Need more research*
Tracks the files that have been open or saved using the Windows common dialog box. 

last file opened by specific extension. 

Track the last file and folder opened and used to populate date in recent menus of start menu.

```
NTUser.dat\software\Microsoft\windows\currentVersion\Explorer\ComDlg32\OpenSavePidlMru
```

## LastVisitedMRU

Tracks the last folder an application have open or saved an file in using the windows dialog box.
Any other of opening or saving an file is not saved in this key.
If you see an GUID instead of an executable name it an standard windows application. 

```
NTUser.dat\software\Microsoft\windows\currentVersion\Explorer\ComDlg32\LastVistedPidlMru
```

### XP search

XP search assistant

Interpretation

* 5001 = search internet
* 5603 = all or part of a document name
* 5604 = word or phrase in a file
* 5647 = printers, computers or people

```
NTUSER.dat\software\microsoft\search\assistant\ACMRU\#
```

### Search database

info on files, email

Tools

* libesedb
* ese database view
* sanderson ESE db extension
* Lostpassword search index examiner

```
\Programdata\microsoft\search\data\application\windows\windows.edb
```
