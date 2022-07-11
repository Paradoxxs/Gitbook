# IOS

Covers the mobiles devices created by Apple (iphone, ipad, ipod, apple watch)  

## File system  

Apple file system (APFS) is the default file system on IOS, tvOS and watchOS,
Optimized for SSD with latency in mind, allow for faster boot and better interaction speed, an Full disk encryption and data protection

### Data

User data is stored in the NAND flash memory,
Apple device do not have SD card,
Format

- Sqlite
- Plist
  
### Application sandboxing 
Apple uses sandboxing to ensure if you download an malicious application.
This will limit the amount of interaction the app can do with the system. 
Enables the user to interact with an application without accessing the file system, by containing within a specific container.

### Encryption

Device
- Uses AES 265-bit encryption, and with secure enclave brute forcing is no longer an option, without specialized software

Data
- Each user created file have a file key, this file key is assigned and controlled by the master key, the class key protects the file key and the device passcode protect the class key. When you choose to wipe and IOS device it deletes only the master key, leaving the data encrypted and unable to be reversed. 


## Application

IOS uses .ipa file extension, which is an archive container that can be extracted. The phone needs to be jailbreak to be accessed, It requires an Mac to analysis the files.

## Forensic acquisition

Whem performing acquisition it ideal to obtain the deepest level of data supported. And then maybe do the other method that do better job at parsing and display the data from the phone.

### Steps 
- Determine ISO type
- FFS - Checkm8 possible or checkra1n
- Obtain backup
  - Make sure the tool did not encrypt the backup and forget to decrypt it.
- Crash logs from iBackupBot
- Cloud data
- SysDiagnose and other apple profiles

### Jailbreak
The process of exploiting flow in the device to install software on the device, 
Will allow you to get full access to the device

Checkm8 run in RAM, not permanent.
Checkkra1n leaves permanet trace on the phone.

### Imaging types

#### Logical
Obtaining specific content of the logical storage that live inside the file system.

#### Full file system

Get full access to the phone file system, including those that are normally protected by the device

#### Physical

Bit by bit access to the device, not possible because of security


## Analysis

Unlike Android device, the IOS system is an closed platform, which only apple engineer have access to the source code. Because of this and the control Apple have over the platform the file structure is easier simpler to understand. 

To speed up the analysis of [ILEAPP](https://github.com/abrignoni/iLEAPP) will help you parse and present some of the information from IOS dump. It important to note that no tool will parse all the data. 

E.g. Application that not parsed it up to the analysis. To understand the structure of the tables within database, and the context around the information within the application.

In the reverse engineering part of the book I will go more into depth about how to reverse a mobile application.

### Sysdiagnose logs

Logs created by Apple to help diagnose issues, It have to be triggered by the user
The Log files will be in a zip archive file format.

MacOS

````
    /Users/<username>Library/lobs/crashReporter/MobileDevice/[Device_name]
````    

Windows
````
%userprofile%\appdata\roaming\app computer\logs\crashReporter\mobileDevice\[device name]
````


Tools
[cheeky4n6monkey/iOS_sysdiagnose_forensic_scripts](https://github.com/cheeky4n6monkey/iOS_sysdiagnose_forensic_scripts)

### KnowlegdeC

Require full file system, contains information about how the user interact with the phone.
Contain a lot of important information.

information:
- Application usage, install, activity
- Safari history
- Power status
- Lock status
- Battery usage
- Audio status

## Application

App can be installed are installed from the Apple app stored
IOS application files have the .ipa extension, which is a similar to a zip container which can be unpacked. 
Apps are identified by their GUID, one way to identify the application behind is using the application state database. 
Bundle id to application Bundle Id Finder

### Application state database
 SQLite database that stored information on all currently installed application.  
````
/private/var/mobile/libray/frontboard/applicationstate.db 
````

App bundle

The location of the bundle used to install the application.

````
/private/var/containers/bundle
````

App data

User generated data can be found in the following directory.

````
/private/var/containers/Bundle/Application/*GUID directory*/
/private/var/mobile/Containers/Shared/AppGroup/*GUID directory*/
/private/var/mobile/Containers/Data/PluginKitPlugin/*GUID directory*/
````

Other

app can also store data in other subfolders like.

````
/private/var/mobile/share/appgroup
````

            
## Locked device

### Passcode

The easiest is to unlock the phone with the code.

Asking for the password might be one way to achive it, otherwise you have to try and cracking the device code.

### Lockdown file

If there is trust between the computer and the mobile device, you might be able to find the lockdown file on the computer, they might not give anything but worth a try.

Win
````
ProgramData\Apple\Lockdown
````

Mac
````
/private/var/db/lockdown
````

### Before First Unlock  (BFU)

Allow you to acquire a limited amount of data, by using a jailbreak solution like checkra1n and checkm8,
Will give access to some user data, OS and app usage, and OS config files.
It is possible to find the user password within which will unlock the device and gain will access.

### Premium service - Law enforcement only

Premium service that only avilable to law enforcement to try and open the device up.

- GrayShift Graykey
- Cellebrite premium

### Apple watch

Small write device  which run Watch OS, must be parried with an iPhone,
It important not to pair the device with a new phone, as it will result in a wipe.

Design
    The device has an Internal storage
    Connector - Wifi, Bluetooth and cellular
Acquisition
    You can extract the data manual

## iCloud

Apple provide 5gb of free storage to user, which is in most cases not enough for backup.

To acquire any data from iCloud you need the username and password to access the data, and possible MFA. MFA can prevent cloud pulls

Beware multiple pulls of cloud data can force the user to reset their password.

### Sync

Allows data to be updated and synced across all devices, the flow is device pushes data to iCloud, and then the other IOS device pulls the data.

One of the difficult parts of sync is what device pushed the data to the cloud.
**CloudConfigurationDetails.plist** may reveal the truth.
Sync data can result in weird timestamp because the data is not origin from the device in question

## Apple continuity

Allows for instantaneous activity on multiple devices, allows for handoff copy text from a document in one device paste to another device
This will results in multiple potential sources of evidence, Will raise the question of  What device was used to create the data.

## IOS backup

There exist two types of backup iTunes and iCloud backups.
The backup folder is segmented into a different folder by GUID these folders contains info.plist which will define the backup device.

When creating a backup of a device it is important to encrypt the backup otherwise you will only get limited amount of data.

Deleted data will not be parsed but can be viewed by looking at the file using a hex viewer.

Sysdiaganoise logs can tell when the backups was created.
 
### Locked backup files

Crack password using hashcat and then use AnyTrans to unlock the backup.
Another option is use the Reset All settings will allow you to create a new backup for which you can choose the password of the backup.

Tools
- Elcomsoft Phone breaker

## Detecting Evidence destruction

Examine creation timestamps of (sms.db, callhistory.storedata, addressBook.sqlitedb, voicemail.db, notes.sqlitedb), It will be the same as the first time the device get booted up.

.obliterated file exists (not always present)
