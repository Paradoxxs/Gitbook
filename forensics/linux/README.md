# Linux

## File system

### Ext2, Ext3, Ext4

This is the local, or default, Linux file system. The root filesystem is generally mcapped to the entire Linux distribution. The Ext3 file system is an excellent update of the previously used Ext2 file system; it uses the transactional file writing operation.  Ext4 is an extension file that supports Ext3 information and file attribution.

### ReiserFS

The file system problem is solved by saving a lot of small files at once. There is a good laugh by the file manager, and the permission of the compatible file, the storage of the file code, the file contains metadata in the mode of not using the large file system due to its size.

## XFS

The XFS file system works well and is widely used for file archiving. This file system type is popular on IRIX servers.

## JFS

IBM developed this file system, and it has become a file system that is used on almost all Linux distributions

## Hierarchy
https://remnote-user-data.s3.amazonaws.com/RQbhqobGCDIa1NmT5iAhOnrySnw8h7NfGf6opnBuHjd1Utw_qXzqnr7c0od8LaDAg7E9w8z59B7MtJCTQHEWOGLR0iucW1Kpl6AZ6okILIl8RfO9J0hnaZK_dKaDuHog.png 


# Network

## netstat

TCP/Ip network utility tool about network connections
````
netstat -antp
netstat -la 
netstat -la | grep “LISTEN” “ESTABLISHED”  
````

## logs

````
/var/log/messages
````

# File execution & information

## Conjobs
Description
Scheduled jobs
````
crontab -l
/etc/cron.*
````

## Processes

````
ps auxf
pstree
````

## SGID
 
find user ID files
````
find / -perm -6000 -type f  
````

## SUID 

Find SUID files owned by root and check entries
````
find / -perm -4000 -user root -type f  
````

## Application used to open file
````
/home/user/.config/    
/home/user/.local/share
````

# User activity

## Users
````
/etc/passwd
/etc/shadow
````

## Command history

Tracks user bash command history activity,
It only get written to the file once the user have logged off the system.
````
/Home/{user}/.bash_history
````

## Autn
Description 
Log of authentication to the server 
````
/var/log/auth.log
/var/log/secure (Redhat and cenOS)
/var/log/utmp
````

## Failed logon

Contains data on all fizzled login attempts, valuable for picking up bits of knowledge on attempted security penetrations; for example, those seeking to hack login certifications, just as animal power assaults.  
btmp log keeps track of failed login attempts   
````
/var/log/faillog
/var/log/btmp
````

## Groups 
```` 
/etc/group
````

## Installation of software
Description
Track installation of system and software packages
````
/var/log/yum.log
/var/log/dpkg.log
/var/log/apt/history.log
````

## file modification

Will find all files that have been modified the last 5 days.  
````
find / -mtime -o -ctime -5 
````
## sudo command activity

````
/etc/log/auth.log
````


# System info

## boot logs

Contains info about booting and messages during startup  
````
/var/log/boot.log
````

## Kernel logs

contains info about kernel logs. This log is important for investigating custom portions.  
````
/var/log/kern
````

## Version
Description
Identity the distribution of kali
````
/boot
/etc/issue
````

## system activity logs
Description
Track non-kernel boot errors, app service errors and log collection during system startup
````
/var/log/messages
````

## Journal database boots
````
journalctl ‒list-boots
````
# apt install respository sources

````
/etc/apt/sources.list.d/
/etc/apt/sources.list
````

## Session name
````
/var/log/auth.log
````

## hosts file
lokal DNS table
````
/etc/hosts
````

## Sleep information

````
/var/log/syslog
/var/log/dmesg*
/var/log/auth.log
````

## root UUID
````
/var/log/dmesg*
````

# External drive

## dmesg

Contains messaging that identifies gadget drivers. The order dmesg can be utilized to see messages in this record.  

````
/var/log/dmesg
````

# Persistance

## Cron jobs

Allow for script, command, binaries, etc to be executed within a define interval. 
```` 
/etc/cron*
````

## SSH keys authentication

Paste in the public ssh key, it will allow you to ssh as that user if you have the private key, whichout knowing the user password 
````
/{user}/.ssh./authorized_keys
````
# Other

## HTTP server logs

Store all types of logs for an Apache HTTP server, including access logs and error logs. The error_log file contains all bad requests received by the http server. These mistakes incorporate memory issues and other framework-related blunders. The access_log contains a record of all solicitations received via HTTP.  
````
/var/log/httpd
````

## Imaging

The dd command is a built-in command-line utility used for creating image files of the data stored in disks. You can also use the md5sum command to create an MD5 checksum of the newly created image, which authenticates the accuracy of the copied data, to perform forensics on the transferred data along with the dd command. This tutorial discussed how to use the dd and md5sum tools in a forensics context to ensure the accuracy of copied disk data.

Parameters
- bs=B: This parameter sets the number of bytes B that can be read or written at any time when creating a disk image file. The default value of bs is 512 bytes.
- cbs=B: This parameter sets the number of bytes B that can be converted at a time during any process.
- count=N: This parameter sets the number N of input blocks of data to be copied.
- if=DEST: This parameter takes the file from the destination DEST.
- of=DEST: This parameter saves the file to the destination DEST.
- If: The path to input the image of the file or drive to be copied.
- of: The path to output the image file obtained from the if
- bs: The block size; in this example, we are using a block size of 1k or 1024B.

### Steps
1. View available disk
````
df -h  
````
1. Create MD5 checksum of the disk using the md5sum command 
````
md5sum /dev/sdb1  > /media/originalMD5  
````
3. Create image file of the disk using the dd command
````
dd if=/dev/sdb1 of=/media/diskImage.img bs=1k  
````    
Do not try to read or open the disk image file, as it is the same size as that of your disk, and you may end up with a handed system. Also, be sure to specify the location of this file wisely due to its larger size.  

4. Create MD5 checksum of the image file using the md5sum command
````
md5sum /media/diskImage.img > /media/imageMD5  
````
Compare the MD5 checksum of the disk image file with the MD5 checksum of the disk

5. Restore the disk from the disk image file
````
dd if=/media/diskImage.img of=/dev/sdb1 bs=1k  
````
6. Create MD5 checksum of the restored disk
````
md5sum /dev/sdb1 > /media/RestoredMD5  
````
7. Test MD5 checksum against the altered image file
````
echo “abcdef”→/media/diskImage.img  
md5sum /media/diskImage.img > /media/changedMD5  
````
8. Compare all the MD5 checksums

````
cat /media/*MD5  
````




#### Mounting E01 on Linux

1. sudo ewfmount {image} {mount directory}
2. sudo mmls {mount directory}/ewf1
3. Look for the sector that have the largest length that not an meta slot.
4. calculate the byte offset, take the sector start offset that was found in the previous step and multiple it with the unit byte sector e.g. {start \* 512}
5. sudo mount -o ro,loop,offset={offset in byte {mount directory} {logical mount directory} norecovery parementer might be need to mount
6. sudo chroot {logical mount directory} - will change the machine root directory to the new logical drive, will act is if you log into the machine
7. exit - can be used to logout of the system again
8. umount - unmount the directory from the system
