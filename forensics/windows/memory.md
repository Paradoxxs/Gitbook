# Memory



* There exists two type of hibernation file full and reduced, Both is a compressed copy of RAM Full occure when the computer hibernation, which happens when battery get to a certain point.
* There will be created a new smaller hibernation file at reach reboot, to allow for fast startup which is on by default.
*

![](https://remnote-user-data.s3.amazonaws.com/kAsejjxHq94r3yoA\_LGM7FteJanf0ryxGdPMvDVboSeyvqIKIyhU\_7iArh08Aqe8btPUkocjKVpRYS9ywxcPHae8bwk4cou1oQxjz4r0iPI-p\_wAo-C0kCPGhu8RDua-.png)

#### Tools

Dump memory\
F-Response\
Belkasoft live ram capture\
Magnet Forensics RAM capture

Decompress\
Volatility imagecopy\
Comae hibr2bin.exe\
Arsenal Hibernation recon

Analysis\
Volatility



### Locations

#### Hibernation files

Compress RAM image

```
%systemDrive%\hiberfile.sys
```

#### Page files

Compress RAM image

```
%systemdrive%\pagefile.sys
```



#### memory dump files

```
%windir\memory.dmp
```
