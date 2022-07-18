---
description: Focus on AWS, google and Azure. 
---

## Cloud bucket

It frequently seen company have misconfigured bucket. Exposing sensitive to the public.

### Cloud enum

[Cloud enum](https://github.com/initstring/cloud_enum) tries to enumerate public resource within AWS, azure and google cloud. 

````
./cloud_eum.py -k domain
````
````
usage: cloud_enum.py [-h] -k KEYWORD [-m MUTATIONS] [-b BRUTE]

Multi-cloud enumeration utility. All hail OSINT!

optional arguments:
  -h, --help            show this help message and exit
  -k KEYWORD, --keyword KEYWORD
                        Keyword. Can use argument multiple times.
  -kf KEYFILE, --keyfile KEYFILE
                        Input file with a single keyword per line.
  -m MUTATIONS, --mutations MUTATIONS
                        Mutations. Default: enum_tools/fuzz.txt
  -b BRUTE, --brute BRUTE
                        List to brute-force Azure container names. Default: enum_tools/fuzz.txt
  -t THREADS, --threads THREADS
                        Threads for HTTP brute-force. Default = 5
  -ns NAMESERVER, --nameserver NAMESERVER
                        DNS server to use in brute-force.
  -l LOGFILE, --logfile LOGFILE
                        Will APPEND found items to specified file.
  -f FORMAT, --format FORMAT
                        Format for log file (text,json,csv - defaults to text)
  --disable-aws         Disable Amazon checks.
  --disable-azure       Disable Azure checks.
  --disable-gcp         Disable Google checks.
  -qs, --quickscan      Disable all mutations and second-level scans
  ````


### Cloudstorage finder

[Cloud storage finder](https://github.com/digininja/CloudStorageFinder)
Search digital ocean spaces, AWS, and google storages. 
The project is split up in smaller ruby script each focusing on a single task

*AWS*
````
Bucket_finder.rb -r all wordlist.txt
````

*google*
````
Google_finder.rb -r all wordlist.txt
````
*Digital ocean storage*
````
./space:finder.rb -r all wordlist.txt 
````

## Authentication

Tries to identify if authentication to cloud service have been set correctly up.

### MFASweep

[MFASweep](https://github.com/dafthack/MFASweep) is a PowerShell script that tries to log in Microsoft service using a set of valid credentials to identify if MFA is enabled correctly. The goal is to test if conditional access policies and other MFA settings have left single factor access open.


Perform MFA sweep check
````
Invoke-MFASweep -Username username@domain.com -Password password 
````

# Gits

Are repositories for sharing code between developers

## Gitrob

[Gitrob](https://github.com/michenriksen/gitrob) tries to find sensitive files that have ben pushed to pulic respositories on Github.\
It does this by cloning the respos and iterate through the commit history and flag files that matches signatures for petentially sensitive files.

````
gitrob target {git respos link}
````