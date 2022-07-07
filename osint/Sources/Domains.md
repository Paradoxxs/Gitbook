# Domains

Domains are away to translate an IP-address to something more rememberable. You have to register your domain with an internet corporation for assigned names and numbers (ICANN).

Most often are domain related to an website or service of some kind.

## Whois

When domain names are registered with ICANN data about who registered it is submitted. User can make their data private to hide it from the public. This data can also be false, old, wrong, etc. because there no enforcement of the data provided have to be valid.

The easiest way to view WhoIs information is using the **whois** command on Linux. other wise site such as [viewdns.info/whois](http://www.viewdns.info/whois).

Because the information can change overtime, which is why historical data lookup could be used to identify a person.

**Historical Whois**:

[whoisology](https://whoisology.com/)

[whoxy](https://www.whoxy.com/)

[domainiq](https://www.domainiq.com/)

Have historical Whois information, it will also try to identify other sites owned by the same person, It does comes with an price.

**Reverse Whois**

It possible to perform reverse lookup on the registrant name that was used [ViewDNS reverse WhoIs](https://viewdns.info/reversewhois) Have this feature.

## Hosting

Domains are linked to an IP address. To identify the IP address it point to at the current moment you can use the **nslookup** command, but this will only gain you the current IP address it pointing to. Which is why looking at historical IP information can be used to gain useful information.

Historical domain IP addresses:

[Viewdns iphistory](https://viewdns.info/iphistory/)

[PassiveDNS](https://passivedns.mnemonic.no/)

## DNS

Domain name service are how domain names are translated to IP addresses and back. It common for multiple domains to be tied to a single IP address, with DNS queries we can find those domains. An domain records contains multiple fields of data that can give us insight.

| DNS record | Purpose                              |
| ---------- | ------------------------------------ |
| A          | IPv4 to hostname                     |
| AAAA       | IPv6 to hostname                     |
| CNAME      | Hostname to another hostname         |
| NS         | Name servers of the domain           |
| MX         | Emails server of the domain          |
| TXT        | Any text used for clidation purposes |

```
nslookup {domain}
```

```
DNSRECON -t std -d {domain}
```

#### Zone transfer

Zone transfer is **the process of copying the contents of the zone file on a primary DNS server to a secondary DNS server**. Allowing us to get all domain information such as subdomains.

```
dig axfr {domain}
```

{% embed url="https://hackertarget.com/zone-transfer/" %}

{% embed url="https://dnsdumpster.com/" %}



## Web archive

Record websites in order to preserve websites, allowing one to look back in time to see how the internet have changed over time.

[archive.org wayback machine](https://archive.org/)

[archive.ph](https://archive.ph/)

## Technology

Every website or service is built upon an technology, This is where [BuiltWith](https://builtwith.com/) comes into play, it will try to identify the technology used on the site.

[blacklight privacy inspector](https://themarkup.org/) will look into the website and notify of privacy invasive activity.

When you visit an website you might have notices an icon in the tab bar. This is called an favicon. you are able to find other site which have the same favicon to identify other sites. Before you start you have you calculate the hash value of the icon this is done with [faviconhash](https://faviconhash.com/). The next step is to query the hash value on [shodan.io](https://www.shodan.io) using the query **http.favicon.hash:{hash}**

## Monitoring

You might be interested in if an website changes it appears over time. This is where [Visualping.io](https://visualping.io/) can help you monitor websites and notify you if there are any changes to the site.

## Domain analytics

In order to track usage information of the visitors, and the key words used to find the site. Analytic in form of a number. It common it you own multiple sites to use the same analytic ID to track them all. This allow us to perform reverse search and pivot from one site to the other sites that also owned by the same user

[Analzeid](https://analyzeid.com/) perform cross-reference of multiple of attributes, like IP, analyst id, etc. To identify other website owned by the same person.

[Spy On Web](https://spyonweb.com/) Is one of the tool that will search an domain name and identify multiple sources of information and tries to cross-reference website that have multiple of the same attributes. This allow you to identify that possible owned by the same person.

[Domainiq reverse analytics](https://www.domainiq.com/reverse\_analytics) will also perform reverse search on google analytics ID.

[Hacker target reverse analytics search](https://hackertarget.com/reverse-analytics-search/) Is unique because it also have historical analytics ID.

## SSL certificates

It common for website to have an SSL certificate that allow for secure connection through the HTTPS protocol.

[crt.sh](https://crt.sh) Identify historical certificates this can allow you to identify other domains that have been registered and with who they where registered with. Where it possible to ask the register for information on the person who register the domain.

[Censys.io](https://search.censys.io/) Allow you to search for certificates reuse, or pivot on different pieces of information on the cert to find new information. The good thing about Censys is that it provided in real-time, ensuring that the data is always up to date.

## Robots.txt

Found at the root of the website, it there to instructions the search engines crawler which webpages should not be index by the search engine.

**e.g. http://www.cnn.com/robots.txt**

This file can help us identify folders of the website like beta sites, websites under development, etc. Which we can possible use to identify additional information.

## backlink

Identify website that link to the target domain. [Host.io](https://host.io) will identify sites that link to the domain

## Redirects

Website can send http code 301 or 302 which tells the browser that the material you are looking for is at a new location. [Host.io](https://host.io) can also help you identify these.
