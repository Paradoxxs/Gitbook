# persistance

### Login item

Common method for software to automatically be executed when user logon

System preferenaces ⇒ users and groups ⇒ login items

Tool

* Knockknock

### Launch items (agents & daemons)

Launch items is a way to persist non-application binaries like software update, background processes, etc. There are two types Daemons and agents.

Daemons are non-interactive and run before the user login.

Agent lunch on user logon and interact with the user session.

To become an launch item the malware needs to create a property list (plist) in specific location, this file will describe the object what is launched with launchd Key : program or program arguments | value : path key : RunAtLoad | values : boolean tell the system to launch the item.

Agents

```
/System/Library/Launchagents
~/Library/LaunchAgents
```

Daemons

```
/System/Library/LaunchDaemons´
```

### Cron jobs

```
Because macOS is based on unix it shares some components this is one of them. 
```

Cron jobs allow for scripts, command, etc. to be executed at define intervals

```
crontab -l 
/private/var/at/tabs
```

### Login/log out hooks

By creating an login or logout hook a script or command will be executed when a user logs in or out of the system. The hooks are stored inside a plist, the key pair to look for is either loginHook and LogoutHook

```
~/Library/Preferences/com.apple.loginwindow.plist  
```

### Dynamic libraries (dylib)

Instead of loading the whole program at runtime into memory, to speed up the execution of application, dunamic libaries allow the program to only load was it necessary at the moment and load the other at runtime when needed. When it comes to malware it will try to piggy-back off another process persistance, by injecting DYLD\_INSERT\_LIBARIES into a process plist

Detection Scan all launch items and application and check the relevant property list for DYLD\_INSERT\_LIBARIES key/value pair\
Tool Dylib hijack scanner

### Periodic

Very similiar to con job requires that the malware have root access

```
/etc/periodic/
```

### at task

At tasks are used to schedule tasks to execute at define time.

```
/private/var/at/jobs
```

### Event monitor rules

The event monitor binary emond at /sbin/emond will load any rules from the /etc/emond.d/rules/ directory. The rule files are in the plist format and define the name, event type, and action to take

```
/etc/emond.d/rules 
```

### Re-opened applications

Allow the user to start up the application that was shutdown when logout. The application to be open again are stored in a plist

```
~/Library/Preferences/ByHost/com.apple.loginwindow.<UUID>.plist  
```