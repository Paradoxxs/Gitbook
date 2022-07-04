# macOS


Apple personal computer, based on unix kernel.

Identifier of mac devices
- Model number
- EMC Number
- Serial number

## Files system

HFS (Hierarchical file system)
- HFS+

APFS (Apple file system)

- Proprietary file system from Apple and utilized in all newer product, and not natively support within Windows OS, as it would requires reversing engineering the technology,
Allow for Native encryption, snapshots.

Local time machine snapshots (APFS)

- Time machine is a utility tool to create backups, it requires the user to activate time machine and use either the local or remote disk to store the backup file. 

Local backup are known as APFS snapshots

Look at Windows forensic fat file system.

## T2 Security chip

Enhance the security of the device by adding dedicated chip to handle security features, ensuring that the data never fit the OS chip, separating the two.
Features
- Automatically encrypt SSD, this also included unallocated space. 
- Secure boot, only allowing verifies OS is trusted by Apple
- Disallow booting from external drive. 

## Apple Extended Attributes

Special metadata created within the macOS, It contain valuable information for an investigators.
It is also responsible for the timestamp within macOS
Windows is not able to view this metadata.

## Native file types

    Mach object file format (Mach-O) - The native executable format for binaries in OS X. 
        At a low level Mach-o files consists of three parts or regions, the header, load commands and data. 

### The header

Will identifies the files as a mach-o file, in there is also contain some basic information about the file such as the target architecture and flag for how rest of the data should be processed. 
Of note the filetype parameter will describe the type of file it is, there exist serveral type of like (0x2:standard exe, 0x6:dll dylib, 0x8: bundle)
tools such as otool with -hv or machoview allow you to view the header of these files.

````
struct mach_header_64 {
uint32_t    magic;          # mach magic number identifier
cpu_tpe_t   cputype;        # cpu specifier
cpu_subtube_t   cpusubtype; # machine specifier
uint32_t    filetype;       # type of file
uint32_t    ncmds;          # number of load commands
uint32_t    sizeofcmds;     # the size of all the load command
uint32_t    flags;          # flags
uint32_t    reserved;       # reserved
}
````

### Load command

After the header section is the load commands which tells how to load and layout the binary in memory, using the otool with -l flag will display the command section.
Load command begin with a load_command structure which have two variables, cmd that tell the type of command cmdsize that say what the size of the command is.

````
struct load_command {
uint_32_t   cmd;        # type of load command
uint_32_t   cmdsize;    # total size of commands in bytes
}
````

Once the binary is loaded into memory by the dyld, the execution begins at the entry point, the way dyld locate the entry point is via the LC_main load command.
The most important function in LC_MAIN is the entryoff which contain the offset of the binary entry point, at load time dyld will add the value to the in-memory base of the binary and then jump to the instruction to kickoff the execution for the bin. 

````
struct entry_point_command {
uint_32_t   cmd;        # LC_MAIN only used in MH_EXECUTE filetypes
uint_32_t   cmdsize;    # total size of commands in bytes
uint64_t entryoff;      # file TEXT offset of main
uint64_t stacksize;     # if not zero, initial stack size
}
````

entry_point_command structure another is LC_LOAD_DYLIB which describes which dyld to load and link, from malware analysis point of view can provide insight into the capabilities of malware, for example a bin that contain a that reference DiskArbitration library may be interested in monitoring USB drivers. 
Serveral key segement when analysing mach-o bin.

- _TEXT - contain executable code and data that is read-only.
- _DATA - data that is writable.
- _LINKEDIT - Information for the linker (dyld) such as symbol, string and relocation tables entries.

### DATA

Consist of the binary code, this data is organized into segments code or data each segment contains one or more section,  different type of code and data goes into each section

- _TEXT : executable code and data that is read-only
  - _text - complied bin code
  - _const - constant data
  - _cstring _ string constats
- _DATA : contains writable data
  - _data - global var
  - _bss - static variables

## Bundle

Are self contain application files with contains everything needed to run the application.
If the file is transfer to a Windows machine it would appear as a folder contain multiple files.

### Subfolder

- _codesignatur - contains code-signing information about the app
- MacOS - Application binary
- Resource - UI elements of the application
- info.plist - The main configuration file

## File vault

Is full volume encryption which can only be decrypted with the user login password or recovery key which is created when first activated. 

## Drive

Fusion drive are Hybrid drive technology by Apple from 2012 to 2020 of having both a HDD and a SSD storage device inside the device, having the OS automatically manage the drive, by having the data used often on the SSD part of the drive.
Aquisition of these type of drive have to be done logical, as physical aqusition of the drive will only aqcure the HDD partition.

# Analysis
  
Because Apple have develop many  proprietary technology it best to do the acquisition and analysis through an mac device, because no other forensic tool has properly parsed or utilized the correct timestamps for macOS  

## Steps by steps

1. Pre-search intel
   - Number and types of Macs (MacBook, iMac, or Mac Pro)
   - Operating System Version (for collecting/processing volatile data and Copy Over Procedure)
   - Type/s and the number of ports
   - Does it contain a T2 Security Chip with Secure Boot?
   - Does it contain an Apple Silicon processor?
   - Is FileVault Active?
   - Can passwords be obtained?
 
2. Isolate
   - Assign one trained Digital Evidence Collection Specialist to handle the electronic evidence to minimize contamination and the Chain of Custody. Prohibit anyone else from handling the devices.  

3. Ask for password
   - Without the password, most security feature in mac will keep you out.

4. Computer on, lock screen active
   - Ask for password
   - Restart to Image RAM - Connect a RAM Imaging Utility to the Mac such as RECON IMAGER. Conduct a soft-restart (do not power off if possible and image the RAM). **Note - This will not work with Macs with Apple Silicon and T2 Security Chips with Secure Boot enabled.*  

5. Computer off
   - Collect the computer using best practices for the collection of electronic evidence. Prepare for imaging.

6. Computer on, desktop assessable
   - look for destructive processes
       - Look for signs of destructive processes such as wiping utilities, erasing free space, etc. If destructive processes are running, options are:
       - Attempt to stop the destructive process. Use Force Quit, if possible (Command + Option/Alt + Esc keyboard combo).  
   collect volatile information
       - Using a trusted and validated tool (not the source computer’s tools), collect Volatile Data such as running processes, network connections, unsaved documents.
   - Check for hidden dekstop or VM
       - Check for running virtual machines and open files on other desktops (macOS supports up to 16). If a Virtual Machine is found running, use the VM software to “Save a snapshot” (keep in mind the will create a new file or could overwrite an existing snapshot). Treat the VM as a new computer following the best practices for responding to a live system for that OS.  
   - Check for encryption
       - When the user is logged in, data on any mounted encrypted volumes are accessible.
       - Check to see if any of the mounted volumes are encrypted (Command + I). If encrypted, copy the data from the encrypted volumes to an HFS formatted volume to preserve metadata (can use “rsync” command) or Live Imaging built into RECON ITR.
       - Using System Preferences -> Security and Privacy -> FileVault, check to see if FileVault is ON or OFF. If found ON, copy the data from the encrypted home directory to an HFS formatted volume to preserve metadata  
   - Image ram
       - Image RAM using tool that support the running mac version
       - Special Note - imaging Mac RAM can sometimes cause a kernel panic and requires the admin password. Make sure that you image Mac RAM last.
   - Obtain datetime
       - With the system OFF, power on the system holding down the Option/ALT key to check for the presence of a Firmware Password (boot level password). If you do not see a lock, power off the system by holding down the power key. If the Mac does not contain Apple Silicon or a T2 Security Chip, power on the system again, holding the (Command + S) keys. Once you see text, you can let go. This is Single User Mode. If the Mac does contain Apple Silicon or a T2 Security Chip, you will need the password to enter Single User Mode. At the command prompt, type: date Power off the system by holding down the power key until the system turns off.  

7. Image mac with T2 security chip and secure boot enable
   - Macs with T2 Security Chips have Secure Boot enabled, preventing booting from any external devices. To image Mac with Secure Boot enabled, put the source Mac into Target Disk Mode by holding down the “T” key on startup. Connect the source Mac to your forensic computer with the proper cable (ex. Thunderbolt) and boot your forensic computer with RECON ITR to image.   
  - Optionally, if you know the password, you can enter the Mac’s Recovery Mode and disable the Secure Boot and Booting from External Media to allow booting.   
  
8. Image mac with apple silicon processor
   - Newer Macs with Apple Silicon Processors will always require the administrator user password. Apple Silicon Macs cannot boot to external media and do not have Target Disk Mode. To image an Apple Silicon Mac, the examiner needs to log into an administrator account and image using any compatible commercial tool like RECON ITR’s Live Imager. Apple Silicon Macs can also be attached to other Macs using the SMB connection available in Sharing Mode.   

# Acquistion 

With the new chipset in Mac computer which does full file system encryption through a dedicated hardware chip it is no longer possible to do a physical acquisition any more.
It important when entering a crime screen that any Apple device can be used to send the kill/wipe to the device. 

## T2 security chip

Dedicated hardware chip for handling encryption key and the encrypt and decrypt of the data, Will most likely not be able to extract anything useful, if you do not have the password, 
Also limits the amounts of attempts to a maximum of 118 attempts  

### Image 
 
The method of acquiring data from a mac depends upon the hardware in question. 
Flowchart
https://remnote-user-data.s3.amazonaws.com/xKcUVfRGTY2EIYwJ40KtRSBno1aAiDqYM5s49i7cgtEdIm-p4xBEr67VTe1XhNKxhpqc0vBf-tFcrL4j5KI7_Lae8xqi98Q5PsLlLY9gKsWH8cieww7OGLWW7o4q9iD4.png 

dd
- Will make a copy of all of the data block and write it to a file. 
dcfldd - Defense computer forensics laboratory dd
- Allows for splitting the output, hashing and verification, process indicator.
dc3dd - Department of defense cyber crime center dd 
- Recommend tool by Sans 
Memory 
Tool 
    osxpmem 


Resources
    Mac Forensics Best Practices Guide | SUMURI Guide 
    Mac Imaging Guide | SUMURI Guide 
    The Art Of Mac Malware 


# Persistance 

## Login item

Common method for software to automatically be executed when user logon

System preferenaces ⇒ users and groups ⇒ login items

Tool
- Knockknock

## Launch items (agents & daemons)

Launch items is a way to persist non-application binaries like software update, background processes, etc. 
There are two types Daemons and agents.

Daemons are non-interactive and run before the user login.

Agent lunch on user logon and interact with the user session. 

To become an launch item the malware needs to create a property list (plist) in specific location, this file will describe the object what is launched with launchd 
    Key : program or program arguments | value : path 
    key : RunAtLoad | values : boolean tell the system to launch the item. 

Agents

````
/System/Library/Launchagents
~/Library/LaunchAgents
````
Daemons
````
/System/Library/LaunchDaemons´
````
            
## Cron jobs

    Because macOS is based on unix it shares some components this is one of them. 
Cron jobs allow for scripts, command, etc. to be executed at define intervals 

````
crontab -l 
/private/var/at/tabs
````    

## Login/log out hooks 
 
By creating an login or logout hook a script or command will be executed when a user logs in or out of the system. 
The hooks are stored inside a plist, the key pair to look for is either loginHook and LogoutHook 

````
~/Library/Preferences/com.apple.loginwindow.plist  
````

## Dynamic libraries (dylib)

Instead of loading the whole program at runtime into memory, to speed up the execution of application, dunamic libaries allow the program to only load was it necessary at the moment and load the other at runtime when needed. 
When it comes to malware it will try to piggy-back off another process persistance, by injecting DYLD_INSERT_LIBARIES into a process plist

Detection
    Scan all launch items and application and check the relevant property list for DYLD_INSERT_LIBARIES key/value pair  
Tool
    Dylib hijack scanner

## Periodic 

Very similiar to con job requires that the malware have root access 

````
/etc/periodic/
````

## at task

At tasks are used to schedule tasks to execute at define time.

````
/private/var/at/jobs
````

## Event monitor rules

The event monitor binary emond at /sbin/emond will load any rules from the /etc/emond.d/rules/ directory.
The rule files are in the plist format and define the name, event type, and action to take  

````
/etc/emond.d/rules 
````

## Re-opened applications

Allow the user to start up the application that was shutdown when logout.
The application to be open again are stored in  a plist  

````
~/Library/Preferences/ByHost/com.apple.loginwindow.<UUID>.plist  
````

## Application/binary modification

Persistance can be achived by mofiying legit app

