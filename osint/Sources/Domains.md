# Domains

Domains are away to translate an IP-address to something more rememberable.
You have to register your domain with an internet corporation for assigned names and numbers (ICANN).

Most often are domain related to an website or service of some kind.

## Whois

When domain names are registered with ICANN data about who registered it is submitted.
User can make their data private to hide it from the public.
This data can also be false, old, wrong, etc. because there no enforcement of the data provided have to be valid.

The easiest way to view WhoIs information is using the **whois** command on linux.
other wise site such as [viewdns.info/whois](http://www.viewdns.info/whois).

Because the information can change overtime, which is why historical data lookup could be used to identify a person.

Historical Whois:

[whoisology](https://whoisology.com/)


## Hosting

Domains are linked to an IP address. To identify the IP adress it point to at the current moment you can use the **nslookup** command, but this will only gain you the current IP address it pointing to. Which is why looking at historical IP information can be used to gain useful information.

Historical domain IP addresses:

[Viewdns iphistory](https://viewdns.info/iphistory/)
[PassiveDNS](https://passivedns.mnemonic.no/)

## Web archive

Record websites in order to preserve websites, allowing one to look back in time to see how the internet have changed over time.

[archive.org wayback machine](https://archive.org/)
[archive.ph](https://archive.ph/)

## Technology

Every website or service is built upon an technology, This is where [BuiltWith](https://builtwith.com/) comes into play, it will try to identify the technology used on the site.

[blacklight privacy inspector](https://themarkup.org/) will look into the website and notify of privacy invasive activity.

When you visit an website you might have notices an icon in the tab bar. This is called an favicon. you are able to find other site which have the same favicon to identify other sites.
Before you start you have you calculate the hash value of the icon this is done with [faviconhash](https://faviconhash.com/).
The next step is to query the hash value on [shodan.io](https://www.shodan.io) using the query **http.favicon.hash:{hash}**

## Monitoring

You might be interested in if an website changes it appears over time. This is where [Visualping.io](https://visualping.io/) can help you monitor websites and notify you if there are any changes to the site.


## Domain analytics 
