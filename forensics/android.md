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

**Installed packages**

Contains information about the installed packages, included deleted apps
````
/data/com.android.vending/database/localappstate.db
````

**App APK**

Location of the APK used to install the application.
````
 userdata/app
````
**App data**

 User generated data in the /data/data/{bundle identifiers} directory. Most apps bundle ID name is easy to identify, but that not always the case. An easy way to determine an appliance id is to look in the google play store using an browser play.google.com/store/apps/details?id={bundle id}.

**App data formats**

- SQLite databases.
- XML
- JSON

### Store Structure

The user space is comprised of the Applications layer. This includes the primary phone applications like Contacts, Home, Phone, Browser, and all user functionality features. The system is comprised of the framework, libraries, and the Linux kernel. A comprehensive breakdown of these components is defined in detail in Practical Mobile Forensics, Second Edition. The framework and libraries are essentially the glue that ties everything together.

Internal media

 0 - primary user
 10/11 - Second user
 150 - Secure folder

### File systems

**EXT+**
 used on Android 2.3 and newer, The traditional forensics tool are able to mount the file system.

**YAFFS2** (Yet another flash file system 2)

 When create a dd image of a android that uses YAFFS2 system it important to catch the OOB area (64 byte chunk) some tools requires the section to parse the image.

**F2FS** (Flash-friendly file system)

 Common on some Samsung devices

**RFS** (Robust file system)

 Used by some Samsung devices

**YAFFS2**

 The OOB area (64byte chunk) needs to also be extracted otherwise some tools will not be able to parse the data.



### Security

Full disk encryption, (FDE) Backdoor bypasses exists on older devices.

File-based encryption (FBE) - Two data storage location, Credential encrypted (CE) requires the user to unlock the device), Device encrypted (DE), available during direct boot and when unlocked.

Secure boot

 Turn on by default on newer phones, It ensures only properly signed firmware can be booted, Which prevents flashing bootloaders to gain access.

Secure startup

 Optional, requires the user to enabled it, and only work on FDE devices, It requires the user to select a passcode to boot up the device. Will keep people our from gaining access to the data without the passcode. The encryption will only happen on the phone no where else, no JTAG or chip-off will work.

### Android acquisition

![](https://remnote-user-data.s3.amazonaws.com/j8CU6\_E1XIpajgE50zhunK3LXo91zhzAzc7aJfrFJabLbD5aTkxQ7Nl3pOfaPG2iU6oF3NY4WOsbS6b70mAsEz3umMN757MBeyKX\_FWlDSpSAyXpRIOWkQO8rVZD1eKy.png)

**Android debug bridge (ADB)**

 To put a android phone into developer mode, it have to be unlocked to be enabled
 Allows the device to communicate with the forensics workstation
 Must be enabled to access the device by most method
 Verify app through USB should be disabled because some forensics tools what to install application on the phone to gain access.
 Root access is required to pull the /userdata partition
 Tools
   Android debug bridge - command line utility, allows for pushing and pull of data from the phone.

**Rooting Shell**

 None permanent root lost after the device is rebooted, allows access via Linux shell. It very common method for commercial forensics tools, if done incorrectly could brick the device.

## Locked device

Work flow
- What keeping you out FDE, DBE or secure boot
- Crack passcode if possible
- Try BF
- Attempt multiple acquisiton methods


Device\_policies.xml
- Active-password policy
  - Gesture or pattern = 65536
  - Simple 4 digit pin = 131072
  - Complex pin = 196608
  - Alphabetic password = 262144
  - alphanumerical password = 327680
  - Complex password 393216

## Beyond tools

 Search for \.apk files for installed application Android manifest.xml contains information about the application, and the permissions, unique identificeres, etc.

Locate application data
- Userdata/dalvik-cache/arm (.dex, .oat and art files)
- Userdata/dalvik-cache/profiles - metadata for installed apps
- Userdata/system/packages.xml - application permission
- userdata/system/packages.list - contains file path for the application
- com.android.vending/database/library.db - Google account used to download apps
- /data/com.android.vending/database/localappstate.db - Contains information about the installed packages, included deleted apps
- Batterystats - Device batterystate, what draining the battery, etc.

## Detecting Evidence destruction


Usage stats are logged on weekly basis, by looking at the newest creation timestamp in the first week it will tell when the device was first booted up. 

````
/data/system/powermanager
/data/system/usagestats/0/weekly/
````

Missing SD card can be proven to existence by examining **external.db**

## References

 [Android Third-Party Apps Forensics | SANS Poster](https://www.sans.org/posters/android-third-party-apps-forensics/)
