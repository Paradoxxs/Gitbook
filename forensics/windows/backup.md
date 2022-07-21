# Backup

#### Shadow copy

Snapshot are staggered by typically one each week or when major changes happens - Size : 3-5 % disk space.\
Backup of previous version of Windows\
Allow one to revert to previous version of the computer.

Tools:

* Manget forensics IEF
* VSC toolset
* Libvshadow
* ShadowExplorer
  
List available shadows copies
Replace # with the drive letter to list the shadow copy within that drive l
```
vssadmin list shadowstorage /for#:
```
You can identify the location by looking at *Shadow copy volume*
Using symbolic link will allow you to interact with the shadow copy./
To do that we can use the mklink command

````
mklink /d C:\shadowcopy \\?\GLOBALROOT\Device\HarddiskVoulmeShadowCopy#\
````

I recommend using *ShadowExplorer* to interact with shadow copies instead of commandline tools.