# User activity

### Search history

Stores user explorer search history or start menu

```
ntuser.dat\software\microsoft\windows\CurrentVersion\Explorer\wordwheelQuery
```

### Typed path

The path typed in the explorer address bar.

```
ntuser.dat\software\microsoft\windows\CurrentVersion\Explorer\TypedPaths
```

### OpenSaveMRU

Tracks files that have been opened or saved within a Windows shell dialog box. Save or open dialog box, last file opened by specific extension. Track the last file and folder opened and used to populate date in recent menus of start menu.

```
NTUser.dat\software\Microsoft\windows\currentVersion\Explorer\ComDlg32\OpenSavePidlMru
```

### XP search

XP search assistant

Interpretation

* 5001 = search internet
* 5603 = all or part of a document name
* 5604 = word or phrase in a file
* 5647 = printers, computers or people

```
NTUSER.dat\software\microsoft\search\assistant\ACMru\#
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
