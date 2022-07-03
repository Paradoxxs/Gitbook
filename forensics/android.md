---
description: Basic understanding of internals workings of the Android system.
---

# Android

## Design

Android operating system is a open source and based on Linux kernel. The android version of the device can vary widely because it be modified by the mobile developer, plus it up to the manufacturer to allow for new update to be installed, which is why you can see all version of Android and you need to be prepared for it.

User data may be stored internally and externally on Android devices. The internally stored data is saved to the NAND flash memory. The NAND is non-volatile memory, which means the data is not lost when the smartphone loses power. The NAND stores the bootloader, operating system, and user data. Although application data may be open and present in RAM, it is only temporarily stored in RAM while in use. The actual application data is stored on the NAND flash memory or the SD card inserted in the device. A RAM capture may be possible on some Android devices, which renders data that will no longer be available when the device is rebooted or powered off.

### Application

Android app can be installed from Google play store or other app stores. Apps are organized based on categories (communication, social network, productivity, etc).

Android uses the APK file extension, which is an archive file package based on JAR files format, which can be unzipped. It will container the compiled java or kotlin code, with Java the code can be decompiled to get better insight into the application.

### File location

Installed packages

Contains information about the installed packages, included deleted apps

* /data/com.android.vending/database/localappstate.db

App APK

* userdata/app

App data

* User generated data in the /data/data/{bundle identifiers} directory. Most apps bundle ID name is easy to identify, but that not always the case. An easy way to determine an appliance id is to look in the google play store using an browser play.google.com/store/apps/details?id={bundle id}.
* userdata/data/
* /data/media/ - Requires permission to read and write
* /MNT/ or /NONAME/

### Data storage formats

* SQLite databases.
* xml
* JSON

### Store Structure

The user space is comprised of the Applications layer. This includes the primary phone applications like Contacts, Home, Phone, Browser, and all user functionality features. The system is comprised of the framework, libraries, and the Linux kernel. A comprehensive breakdown of these components is defined in detail in Practical Mobile Forensics, Second Edition. The framework and libraries are essentially the glue that ties everything together.

Internal media

* 0 - primary user
* 10/11 - Second user
* 150 - Secure folder

### File systems

EXT+

* used on Android 2.3 and newer, The traditional forensics tool are able to mount the file system.

YAFFS2 (Yet another flash file system 2 )

* When create a dd image of a android that uses YAFFS2 system it important to catch the OOB area (64 byte chunk) some tools requires the section to parse the image.

F2FS (Flash-friendly file system)

* Common on some Samsung devices

RFS (Robust file system)

* Used by some Samsung devices

YAFFS2

* The OOB area (64byte chunk) needs to also be extracted otherwise some tools will not be able to parse the data.

Format

* SQLite, xml, dat, etc.

### Security

Full disk encryption, (FDE) Backdoor bypasses exists on older devices.

File-based encryption (FBE) - Two data storage location, Credential encrypted (CE) requires the user to unlock the device), Device encrypted (DE), available during direct boot and when unlocked.

Secure boot

* Turn on by default on newer phones, It ensures only properly signed firmware can be booted, Which prevents flashing bootloaders to gain access.

Secure startup

* Optional, requires the user to enabled it, and only work on FDE devices, It requires the user to select a passcode to boot up the device. Will keep people our from gaining access to the data without the passcode. The encryption will only happen on the phone no where else, no JTAG or chip-off will work.

### Android data acquisition

![](https://remnote-user-data.s3.amazonaws.com/j8CU6\_E1XIpajgE50zhunK3LXo91zhzAzc7aJfrFJabLbD5aTkxQ7Nl3pOfaPG2iU6oF3NY4WOsbS6b70mAsEz3umMN757MBeyKX\_FWlDSpSAyXpRIOWkQO8rVZD1eKy.png)

### Data aqusition

Android debug bridge (ADB)

* To put a android phone into developer mode, it have to be unlocked to be enabled
* Allows the device to communicate with the forensics workstation
* Must be enabled to access the device by most method
* Verify app through USB should be disabled because some forensics tools what to install application on the phone to gain access.
* Root access is required to pull the /userdata partition
* Tools
  * Android debug bridge - command line utility, allows for pushing and pull of data from the phone.

Rooting Shell

* None permanent root lost after the device is rebooted, allows access via Linux shell. It very common method for commercial forensics tools, if done incorrectly could brick the device. It more common to brick the device then shell root. Full root
* Permanent root utilizes shell root to get full device root, Install SU to /system/bin.

what can go wrong

* /userdata partition can be wiped during root process
* Device brinking
* Traces will be left behind
* Forensicsilly sound?

## Google

* Requires username and password and possible MFA to gain access.
* User will be alerted when pulling data from cloud.
* Google was user password even if you select no.
* Optional feature that the user can sign-up too.
* Features
  * Remote wipe
  * Find my device
  * Backup is automatic if the phone is sign-up to google.
* Locked device
* Work flow
  * ![](https://remnote-user-data.s3.amazonaws.com/XNwhdtv64OHAwKE5NuIT5915xLzhZHlgs3Ip0Vo-z44WXcfrF-U9LeEz5TNwW\_dxTYNjBFayfuTpLA7cCeqUEmtPC82VwOnPBftyHj6WBV2WuYJYCrs5NMs8HIR\_gww4.png)
* Device\_policies.xml
  * Active-password policy
    * Gesture or pattern = 65536
    * Simple 4 digit pin = 131072
    * Complex pin = 196608
    * Alphabetic password = 262144
    * alphanumerical password = 327680
    * Complex password 393216
* Acquisition steps
  * Logical/Backup - smallest footprint
  * File system backup
  * if you are stuck try multiple cables, they might be broke.
  * Root the device - will leave are large footprint
  * Acquire the SD card through the device and SD card and SIM card separately (after created image.
  *
* Forensic acquisition
  * Logical
    * Supported by most tools
    * fast
    * sometimes just a backup
    * may install agent on device
  * Filesystem/backup
    * Not supported by all tools
    * ADB usually required
    * Must be unlocked
    * Provides access to native files
  * Physical
    * ADB requies
    * RAW image, may not be decoded or parsed by aqusition tools
    * Encryption or MDM can cause problems
    * Recovery of deleted data - Requires manual carving and examination.

## Analyses

Triage

* Examine installed apps
* Parsed browser artifacts
* Search the parsed databases for keywords
* Triage parsed location, and validate.
* Determine what requires manual examiniation

Deep dive

* Conduct keyword search for username/accounts
* Examine all tables and preference files in application directories
* Examine SD card or media directory
* Carve or manually parse and decode data.

Placing user at the scene of intresses

* userdata/data/com.google.android.locations/files (cache.cell and cache.wifi)
* userdata/data/com.google.android.gsf/databases/googlesettings.db
* Browser history
* Weatherclock.db - track the weather and time were the user at.

Device in use

* Userdata/data/system/simcard.dat
* Userdata/data/com.google.android.gms/shared\_prefs/checkin.xml
* userdata/data/com.google.android.gms/databases/\*

Garbage collection

* ns.db

Beyond tools

* Search for \*.apk files for installed application Android manifest.xml contains information about the application - permissions, unique identificeres, etc.
* Locate application data
  * Userdata/dalvik-cache/arm (.dex, .oat and art files)
  * Userdata/dalvik-cache/profiles - metadata for installed apps
  * Userdata/system/packages.xml - application permission
  * userdata/system/packages.list - contains file path for the application
  * com.android.vending/database/library.db - Google account used to download apps
  * /data/com.android.vending/database/localappstate.db - Contains information about the installed packages, included deleted apps
  * Batterystats - Device batterystate, what draining the battery, etc.

## Detecting Evidence destruction

* Deleted application
* Deleted files
* Cleared cache
* Removed application
* Selectively deleting messages or history
* Wiped device
  * /data/system/powermanager
  * /data/system/usagestats/0/weekly/
    * Tell about the usage stats on a weekly basis, by looking at the newest creation timestamp in the first week it will tell when the device was first booted up. To convert the date to something more understandable: ( + (time from the file)) / 1000
* Modifying files to advoid detection
* SD card
  * Proof of SD card existence - external.db

## References

* [Android Third-Party Apps Forensics | SANS Poster](https://www.sans.org/posters/android-third-party-apps-forensics/)
