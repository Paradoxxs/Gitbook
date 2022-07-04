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

