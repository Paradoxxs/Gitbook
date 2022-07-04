# File carving and data recovery



The process of retrieving inaccessible, formatted, corrupted or damaged data from a storage medium.

There are two type of carving the first is datastream carving which is carving for small fragment of data and not entire files. These fragments are usually part of a larger file, allow for extracting key evidence when recovery the whole file is not needed or data recovery is not possible.

The second one is file recovery which is the practice of recovering intact files from memory or unallocated space.

The process of file recovery, because many file systems do not delete data when it is deleted. Instead, it simply eliminates their index of them. When looking at the raw bytes, and searching for the specific header (first bytes) and footer (last bytes) of a file or based on a predicted length. [File Signature Database:](https://filesignatures.net/)

## Method

### Overview

File carving can be done in multiple ways, one way is to look at an image, database, etc. in a hex viewer and search for the data you are looking for weather that is using the content of the data or using file signature to locate files of a specific type.

### File recovery

Steps

* Opening the file or image you want to extract data from in a hex editor.
* Search for the file signature header and footer
* Copy the data to a new file

### Data recovery

steps e.g sqlite

* Open database file in hex viewer
* Search for data in the hex viewer

## Location

* Memory/pagefile
* Unallocated space
* Allocated database files
* Database
  * Deleted entries can be recovered from SQLite and ESE database SQLite is notorious for spraying remnants throughout free space.

## Terms

* Block – The smallest size of data units that can be written to storage
* Header – The starting point of the file.
* Footer – The last bytes of the file.
* Fragment – One or several blocks are belonging to a single file.
* Base-fragment – First fragment of file container, the header of the file.
* Fragmentation point – The last block just before fragmentation takes place. Multiple fragments in any file results in several fragmentation points.
* Header-footer technique (or header-“maximum file size”) – The basic strategy here is to carve files based on title and handwriting or total files.

## Tools

* Foremost
* Binwalk
* PhotoRec
* Internet evidence finder
* X-Ways Forensics
* Axiom
