---
description: Identifying alternative location of information
---

In this section is about hunting for information. We will be looking at different sources and tool that can be used to reveal new information.\
Remember when you acquire data any data you need to verify that it legit and not been generated.\
Because of the amount of data that get uploaded everyday to public hacker forum.\
Specially large combo list of data breaches from multiple sites. The question is always how much of it is just duplicated data.\
The best way to sort this is to remove any duplicate files.  

In this section we will only be talking data dumps that public available information.
Which is data that have been stolen from a system that have been released to the internet.

These dump can contain: Username, Emails, password, and much more.

The possession of this information and exercising the method described in this section be seen at illegal by some countries.
What is most important is that you do not use the information to perform any illegal activities.

One of the simplest way to identify if an email or domain have been part of any breaches is the use the [Have I been pwned](https://haveibeenpwned.com/) service. It will also tell you what breaches the credentials have been seen in.

## data usage

These threat actor are just like everyone else, and might reuse password to multiple sites.\
This allow us to pivot, to new accounts which might be registered with new information such as different username, email, etc.\

Another note is that these data leaks contains more then just username and password.\
It could contain information such as IP address that have connected from.\
Account verification information, and etc.

# Cloud bucket

It frequently to see company having misconfigured bucket, exposing sensitive to the public.

## Cloud enum

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


## Cloudstorage finder

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


# Code repositories

Sites like Github, gitlab, etc. are repositories for sharing code between developers.
The good thing about Git sites is that it allow you to look through the history of the code uploaded. This allow you to sensitive information was present in previous commits.

You can look through the logs files of an repository by first cloning the repository and using the *git log* command when standing inside the project folder.

````
git log
````

## Gitrob

[Gitrob](https://github.com/michenriksen/gitrob) tries to find sensitive files that have ben pushed to pulic respositories on Github.\
It does this by cloning the respos and iterate through the commit history and flag files that matches signatures for petentially sensitive files.

````
gitrob target {git respos link}
````



# Data brokers

Data broker providers of information from data breaches and leaks, by collecting, index and make it searchable for an price.


## H8mail

[H8mail](https://github.com/khast3x/h8mail) open source password breach hunting tool that will query multiple data brokers sites for information about the target. You have to bring your own API key for the different service if you want premium service.

Can be installed using pip
````
pip install h8mail
````

usage:
````
python -m h8mail -t username@domain.tld
````

## intelX

[intelX](https://intelx.io/)

Present data It searches in places such as the darknet, document sharing platforms, whois data, public data leaks and others. The free service only give your selective information.

## Breach directory

[Breach directory](https://www.breachdirectory.org/)
Allow through leaks, what makes it difference it provides you with SHA1 hash of the password, which you can crack to identify password.

## leak peek

[leak peek](https://leakpeek.com/)

Service to search in different breaches and leaks, will give you a partial password.


# Leak & dumps

Information that have been made available publicly either through misconfigured services or from hacking attacks. Instead of using data brokers that have automate the process for you for an premium price.\
You also have the option to collect the information yourself.\
The method of during during so we will describe in the section below.

## Hacker forums 

Forums are the social network for the hackers.\
Speically new hackers act without much thinking and there for leave an trail of information that can lead back to their real identity.

This can be used to identify more experience hackers.\
If you are able to get hold of old hackers forum dumps.\
You might be able to link old accounts to threat actors. Where the OpSec was not their priority and identify the true identity of the person.

Another part of hacker forums is when hacker are feuding. This can leads us to golden information if they decided to dox eachother. 

What more about these forums, if they are a marketplace for leads, exploits, dumps and much more for a price.\
What important for us is when leaks and dumps are release for free, allowing us to download the information which we can use in future investigation.\

I will not be mention any forum, not because I find it immoral.\
Instead it because they get taken down, changed, etc. That by the time you read this part it will already been taken down.

## Telegram

Since Telegram added channels to the server they have become quite popular. These channels are publicly available.\
This also include hackers and black market. We see these channels are used as marketplace for threat group to see their information. It frequently to see these channels provides sample data for people to keep them entries. Other channels share public available dumps for you to download.\
The good thing about telegram channel is that you do not have to go through the trouble of earning forum points, to gain access to the data.\
There no official method to search for channels. With some google operators you are able to identify channels. 

```
site:telegram.me "breach"
```
```
site:t.me "breach"
```
There exist sites that tries to index telegram channels, allowing you to search for channels of interest.

Site:
[telemetr](https://telemetr.io/en/channels?channel=leak+data)
[telegramchannels](https://telegramchannels.me/search?type=all&search=breach)
[telegram-group](https://www.telegram-group.com/en?s=breach)


**Dorks**

useful dorks to find information on upload, pastes and doxing sites.

1. Start with intitle:"keyword" (keep the quotes) This scans all of the names of files on Anonfiles and outputs the results that match your keyword.
2. Add "+ site:anonfiles.com" (don't keep the quotes).
3. The Final product should look like this: intitle:"keyword" + site:anonfiles.com

## Paste

Paste site are places where people can post text document they want to share anonymously.
Paste are publicly available to everyone. Which is why you not use it to share sensitive information.
They might not live on forever because the take down by the user, violated TOS.
Because they are public, you might be able to find archive of removed paste. Site such as [archive.org](www.archive.org). Might have saved an copy of the paste site.

### PasteHunter

[PasteHunter](https://github.com/kevthehermit/PasteHunter) that will query publicly available pasted data.

### psbdmp
[psbdmp.ws](https://www.psbdmp.ws/) index paste from pastebin making it searchable for you.

Paste sites:
* [pastebin](https://pastebin.com/)
* [0bin](https://0bin.net/)
* [justpaste.it](https://justpaste.it/)

## Anonymous upload sites

Allow uploading of information anonymously, It often utilized by hacker groups to dump information on target that does not pay the ransomware.\

upload pages:
* [anonfiles](https://anonfiles.com/)
* [filechan](https://filechan.org/)
* [letsupload](https://letsupload.cc/)

These are just some of the anonymous upload sites there exists. When visiting hacker forums or chat application write down the services they are using and try to perform dorks on the site to see if you can gather additional information.


## Doxing

The process of finding and releasing the information to the public on an person.

[doxbin](https://doxbin.com/) collects dox from multiple sites, index and make it searchable for you.

There are sites that monitor for new pastes, scrape and store them.



## BTDigg

[BTDigg](https://btdig.com/) use the search engine to lookup of leak or breaches that are shared using p2p torrent network.


# public accessible storage

This section will be about the different methods of discovering public available data storages. 
This include NoSQL database such as MongoDB and Elasticsearch. And cloud storage platform such as Azure blob storage and similar services.\
The reason we will be looking at NoSQL databases is because they are public available by default. 

I will be using [Shodan](https://www.shodan.io/) to discover publicly available databases.
To optimize the process I will be using [shodan cli](https://cli.shodan.io/) as it allow you to export the information.

Lets start by setting up shodan CLI.

Download shodan
````
apt install python3-shodan
````

Setup API key
````
shodan init {api_key}
````

The shodan download query structure.
````
Shodan download --limit {# of results} {filename}.json {query}
````

Once the data have been downloaded it need to be parsed, allowing us to extract the useful information.
Shodan CLI *parse* will help up this task.
This will take the json output from the previous command and output it to an CSV format.
````
Shodan parse --fields ip_str,port,org --seperator , data.json
````

You are also able to perform historical information about an IP.

````
shodan host --history --format pretty {IP}
````

Because connecting and extracting information from NoSQL database can be difficult I will be using night lion sec [Noscrape](https://gitlab.com/nightlion/noscrape) tool to help perform this task.\
Some of the important parameters:

|switch|description|
|---|---|
|-d| database type [mongo, s3, es]|
|-o|output file of results|
|-tf|csv format of target hosts|
|-t|target ip addresses|
|Mongo|switches|
|-s| type of scrape basic,full|
|es|switches|
|-s|type of scrape scan, search, dump, matchdump|


## MongoDB

*Discovery with Shodan*

Shodan query for IP with mongoDB service
````
Shodan download --limit 50000 data product:Elastic
````

*Accessing the storage*\
[Robot 3T](https://robomongo.org/) is a GUI tool that allow you to access and querying the MongoDB in an easy way.\
IT should be noted that Robot 3T does not allow you to export any data. You can either use command-line tools or purchase a license. It an quick way to get an overview of what information is available.

-WIP- 
Add images of Robot 3T
MongoDB command ?

````
# Connect to database
mongo {IP}

show dbs

use {database}

show collections

use {collection}

# view in json format
db.collection_name.find().pretty()

````

*Scraping*

Using noscrape to collect information from MongoDB.
````
./noScrape.py -d mongo -s basic -tf target.txt -o output.
````

## ElasticSearch

Dicovery of Elastic service using Shodan.\
Shodan query for IP with Elastic service
````
Shodan download --limit 50000 data product:Elastic
````

````
Shodan parse --fields ip_str,port,org --seperator , data.json
````

*Accessing*\

I do not have a handy GUI tool for Elastic. It an good thing that Elatic is a bit easier.

Verify the service is still running
````
curl {IP}:9200
````

List indices

````
curl -X GET "localhost:9200/_cat/indices?v"
````

If you want to dump information from an Elastic database you need a tool called [Elasticsearch-dump](https://github.com/elasticsearch-dump/elasticsearch-dump).

````
elasticdump --input=http://{IP}:9200/index-name --output=index_name.json --limit=10000 -noRefresh
````

*Scraping*

Using noscrape to collect information from elastic search.
The scan method of scraping will list the basic output of each Elasticsearch and output the content of the indicies.

````
./noScrape.py -d es -s scan -tf target.txt
````
You can also use *search* scape method. It will perform an deeper dive into the database by also looking at the mapping table for each inicies within the databases. This is useful for collecting the table headers of the indicies.\
Finally there *dump* method will dump every index as json file by the name of the index.\
To perform an more focus dump the *matchdump* switch will only dump the index if it matches the specified criteria.\
Using the *--filter** switch allow you to specify an txt file with keywords.\
Some good filter kewords are password, username, email, ip, etc.

````
./noscrape.py -d es -tf list.txt -s matchdump --filter keywords.txt
````