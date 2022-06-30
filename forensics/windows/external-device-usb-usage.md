# External device / USB usage

### Plugged in USB (USBSTOR)

Tracks USB plugged into the machine.\
Identify unique USB by vendor, product, and version of a USB device plugged into a machine.\
Allow one to determine the time a device was plugged into the machine.\
Devices that do not have a unique serial number will have an “&” in the second character of the serial number.

MSC:

```
\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR
```

PTP and MTP usb enumeration:

```
\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USB
```

### Device Connection

Determine usage of specific USB devices connected to Windows machine\
Date is set to local time zone. \
Search for device using serial number.\
Setupapi is the plug and play log file, contain the first time it has connected.\
System hive contain the first, last and removal time.



#### setupapi&#x20;

XP:

```
C:\Windows\setupapi.log
```

Win7+:

```
 C:\Windows\inf\setupapi.dev.log
```

#### Registry

* 0064 = First Install (Win7-10)
* 0066 = Last Connected (Win8-10)
* 0067 = Removal (safe eject or pull)

```
System\CurrentControlSet\Enum\USBSTOR\>Vendor_Prod_Version>\>USBSerial#>\Properties\ {83da6326-97a6-4088-9453-a19231573b29}\####
```

### PnP events

Plug and play driver install

Event id:

20001 – Plug and Play driver install attempted

* Timestamp
* Device information
* Device serial number
* Status (0 = no errors)

```
%system root%\System32\winevt\logs\System.evtx 
```

### Drive letter and volume name

Discover the last drive letter for the USB, First you need to identify the serial number via USBSTOR,\
Volume name can be mapped to drive letter via examination of lnk files.\
Key is not cleaned as part of the plug and play cleanup task and retains more historical removable device information.\


The data value is the USB serial number, which can be correlated with ParaentIdPrefix identified in USBSTOR, to get last mount point.&#x20;

XP:

```
SYSTEM\MountedDevices
```

Win7+:

```
SOFTWARE\Microsoft\Windows Portable Devices\Devices
SYSTEM\MountedDevices
```

### Volume serial number

May not be populated if the internal hard drive is a SSD, and only on win7. Allow one to discover the volume serial number of filesystem on the USB.



Use Volume Name and USB Unique Serial Number to:

* Find last integer number in line
* Convert Decimal Serial Number into Hex Serial Number



Knowing both the Volume Serial Number and the Volume Name, you can correlate the data across shortcut file (LNK) and the recentdocs key.

* The Shortcut File (LNK) contains the Volume Serial Number and Name
* RecentDocs Registry Key, in most cases, will contain the volume name when the USB device is opened via Explorer

```
SOFTWARE\Microsoft\WindowsNT\CurrentVersion\ENDMgmt 
```

### MTP device

May or may not create lnk files depending on the app and filetype. Some MTP lnk files will not point back to the MTP source device but instead to the WPDNSE folder on machine only.

```
%userprofile%\appdata\local\temp\wpdnse\{GUID} 
```

### User USB device

unqiue USB device plugged in by the user

GUID will be used to identify the user that plugged in the device, **Last write time** of this key will correspond to the last time the device was plugged into the device by the user.

Look for the GUID in "SYSTEM\MountedDevices NT"

```
\software\Microsoft\Windows\CurrentVersion\Explorer\MountPoints2
```

### Removable devices logs

Using event logs to detect USB events, this needs to be enabled before logs gets written

Events id:

* 2001 (system log) - plug and play driver install attempted
* 4663 (Security log) attempt to access removable storage object
* 4656 (security) Failure to access removable storage object.
* 6416 (Security) A new external device was recognized on the system.

```
windows\system32\winevt\logs
```
