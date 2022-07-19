# Digging for information

In this section we will only be talking data dumps that public available information.
Which is data that have been stolen from a system that have been released to the internet.

These dump can contain: Username, Emails, password, and much more.

The possession of this information and exercising the method described in this section be seen at illegal by some countries.
What is most important is that you do not use the information to perform any illegal activities.

One of the simplest way to identify if an email or domain have been part of any breaches is the use the [Have I been pwned](https://haveibeenpwned.com/) service. It will also tell you what breaches the credentials have been seen in.

## Data brokers

There exists sites which collect, index and make it searchable for an price.
Look at threat intel page to identify sites that provides this kind of service.

**Dorks**

Using dorks to find information on upload, pastes and doxing sites.

1. Start with intitle:"keyword" (keep the quotes) This scans all of the names of files on Anonfiles and outputs the results that match your keyword.

2. Add "+ site:anonfiles.com" (don't keep the quotes).

3. The Final product should look like this: intitle:"keyword" + site:anonfiles.com

# Dumps

## Anonymous upload sites

Allow uploading of information anonymously, It often utilized by hacker groups to dump information on target that does not pay the ransomware.\

upload pages:
* [anonfiles](https://anonfiles.com/)
* [filechan](https://filechan.org/)
* [letsupload](https://letsupload.cc/)

These are just some of the anonymous upload sites there exists. When visiting hacker forums or chat application write down the services they are using and try to perform dorks on the site to see if you can gather additional information.


# Paste

Paste site are places where people can post text document they want to share anonymously.
Paste are publicly available to everyone. Which is why you not use it to share sensitive information.
They might not live on forever because the take down by the user, violated TOS.
Because they are public, you might be able to find archive of removed paste. Site such as [archive.org](www.archive.org). Might have saved an copy of the paste site.

Paste sites:
* [pastebin](https://pastebin.com/)
* [0bin](https://0bin.net/)
* [justpaste.it](https://justpaste.it/)

# Doxing

The process of finding and releasing the information to the public on an person.

[doxbin](https://doxbin.com/) collects dox from multiple sites, index and make it searchable for you.

There are sites that monitor for new pastes, scrape and store them.

[psbdmp.ws]([www.psbdmp.ws](https://www.psbdmp.ws/)) is one such sites that index and archive pastes.
It a free service with API.

[PasteHunter](https://github.com/kevthehermit/PasteHunter) that will query publicly available pasted data.



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