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
