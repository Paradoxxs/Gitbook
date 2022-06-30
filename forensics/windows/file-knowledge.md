# File knowledge

### Thumbcache & thumbs.db

Thumbnails of pictures, office document and folder exist in a database called thumbcache. where each user have their own database based on thumbnail sized.\
thumbcache is created automatically in folders accessed via explorer which contains pictures.

thumbs.db is database of pictures in folder and stores a copy of the thumbnail even if the pictures were deleteted.



tool\
thumbsdb viewer\
thumbscache viewer

thumbs.db:

```
%Userprofile%\AppData\Local\Microsoft\Windows\Explorer
```

### Master file table (MFT)

NFTS hold a MFT of all the files that currently on the system, requires a physical image of the drive.

Tool\
MFT explorer\
MFTEcmd

```
[root]\$MFT
```
