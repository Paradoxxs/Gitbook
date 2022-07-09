---
description: Sqlite a self contained database
---

# SQLite

SQLite database is a self-contained database with a very small footprint making it widely used by browser and mobile devices, which is why it very interesting from a forensics perspective.

It follow very much the same structure as MSSQL and the same standard SQL language query. The way SQLite stores it data is pages of a fixed size, which are specified in the file header.

## Analyzing

### Temporary files

SQLite usage of temporary files are for Journal and Write ahead log (WAL).

SQLite used the journal feature to protect against write errors. That done by taking the page that is about to written to, and backup it up to a temporary file. Allowing the page to rollback to the previous state if the write operation failed.

From version 3.7 SQlite started to employ Write Ahead log (WAL) Which is a opposite version or journal, here new changes are contained to an temporary file. Leaving the database untouched until the log get committed to the database. The default value of committing the log file is at 1000 pages. The reasoning for having a WAL is to increase the speed of I/O transaction, they are not created by default, it is up to the developer to take advantage of the feature.

Which is why when doing forensic on a database, it an good idea to check for WAL otherwise you might not get the newest data available. A key thing to know about WAL is that it can both be active or deleted data. What makes WAL even more interesting for forensic is that they are often unencrypted.

Sqlcipher encrypted error can occur when you try to read a database which need the WAL to access the data, what you can do here is export the WAL and put it in the same folder as the database. Determining is the database is Journaling or WAL can be done by opening the SQLite database file in hex viewer.

Journaling

* Bytes at offset 18 and 19 are 01 01

WAL

* Bytes at offset 18 and 19 are 02 02

### Deleted content

Identify deleted content within the database by looking for missing ID entries.

when information is deleted from the database, it might create a unused pages that are stored on the freelist and is first reused when a new page is required. which allows forensics to acquire the deleted data. The free pages can be viewed by using an HEX viewer, then parsing the information manual. [sqlparse.py by Mari DeGrazia](https://github.com/mdegrazia/SQLite-Deleted-Records-Parser) can help you recover deleted entries within the database for you.

Beside the freelist SQLIte can also store deleted data in unallocated space. They are page fragments containing random bits of data. Very much like unallocated space on a hard drive. This data have to be carved out manual using an hex editor.

### Binary large object (blob)

It an way to storing files within a database as a binary object. The binary have to identified, parsed and then exported from the database, back into a file the system can understand. [SQLite miner](https://github.com/threeplanetssoftware/sqlite\_miner) Will help identify blob object within an database, and parse and export the file from SQLite.

### Timestamp

Timestamp can be stored in the database in one of serval numerical representations, here are some of the common once.

UNIX EPOCH Number of seconds since 1/1/1970

UNIX EPOCH milliseconds Milliseconds since 1/1/1970

**Mac Absolute** are the number of seconds since 1/1/2001 To convert this to epoch, you need to add the number of seconds from epoch to 1/1/2001 (978307200)

```
datetime(column + 978307200, 'unixepoch');
```

**CHROME time** times accuracy in microseconds. to convert the data to epoch requires the data to divide by 1000000.

```
datetime(column/1000000 + (strftime('%s', '1601-01-01')), 'UNIXEPOCH');
```

Tools

* [SQLite browser](https://sqlitebrowser.org/)
* [SQLite miner](https://github.com/threeplanetssoftware/sqlite\_miner) blob object examination tool
* [sqlparse.py by Mari DeGrazia](https://github.com/mdegrazia/SQLite-Deleted-Records-Parser) recover deleted entries in SQLite databases
* [Sanderson forensics toolkit for SQLite](https://sqliteforensictoolkit.com/sqlite-forensic-toolkit/) (Commerical GUI tool)

### Reference

[SQlite pocket](https://www.sans.org/posters/sqlite-pocket-reference-guide/)
