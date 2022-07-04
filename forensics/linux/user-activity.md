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
