

## Google

Google search allows you to search the internet for information. Google allows you to search for file extension locating documents that available to the public.

Google caches website which you can see instead of visiting the website directly.\
It important to add &strip=1 at the end of the URL to ensure that the resource is only loaded from google cache.

### Google dorks
Are templates of advance search options, where can you replace part of the search query with what you find interesting. e.g. company domain
[Google hacking database](https://www.exploit-db.com/google-hacking-database)

Google search operators
| Operator |Meaning|
|---|---|
| site:| Search only on site|
| filetype: | Search for filetype  |
| cache:    | Google cache of page, it important to add \&strip=1 at the end of the url to ensure only resource from google cache is loaded. |
| inurl:    | search for strings in url|
| link:     | Find pages that link to the website|



## Bing

Microsoft search engine
I wind Bing to be an better reverse images search engine then google because of the fact that google does AI/ML on the image to do object recognition and search on the objects within the image instead of the image as a whole.


## Yandex

[Yandex](https://yandex.com/) is the Russian search engine.

## Shodan

[Shodan](https://www.shodan.io/) is a search engine for Internet-connected devices. Where site such as google and bing are more about indexing websites. Shodanqueries every IP address and ports and tries to fingerprint the services that running. What makes shodan standout is that it allow you to search for technology . e.g. lookup devices running Microsoft IIS.

I recommend you buy the membership as it allow you to perform additional query and increase the API request you have. The normal price is $50 but it sometimes on sale for just $5.

## Grayhat warfare

[GrayHat warfare](https://grayhatwarfare.com/) makes public buckets and link shortens searchable by indexing both the bucket and the content within the bucket.
Excellent tool for identifying misconfigured bucket, where you can identify sensitive data that should not be publicly available.

## Scamsearch

[Scamsearch](https://scamsearch.io/) is a search engine for finding scams related to email, username, etc..


## AHMIA

[AHMIA](https://ahmia.fi/) is a TOR hidden services search engine

## Fresh onion

[Fresh onion](http://freshonifyfe4rmuh6qwpsexfhdrww7wnt5qmkoertwxmcuvm4woo4ad.onion/)

## Onion link list

[Onion link list](http://donionsixbjtiohce24abfgsffo2l4tk26qx464zylumgejukfq2vead.onion/onions.php)

## BTDigg

[BTDigg](https://btdig.com/) is an torrent search engine by keywords.\
It can be used to identify breaches or leaks that are being shared using torrent.


## Inurlbr

[Inurlbr](https://github.com/MrCl0wnLab/SCANNER-INURLBR)
allow you to automate dork searching across multiple search engines.\
Inurlbr is a php based, so you have to ensure that you have a PHP enviroment setup. 

Search through all search engines for admin login portal.
````
php inurlbr.php --dork 'inurl:admin intitle:login' -q all
````

Email list
````
php inurlbr.php  --dork '"filetype:xlsx email'  -q all
````
