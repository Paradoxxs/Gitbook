# Domains & Websites

Domains are away to translate an IP-address to something more rememberable.
You have to register your domain with an internet corporation for assigned names and numbers (ICANN).

Most often are domain related to an website or other kinds of services.
Websites will also be discussing in this section of the what kind of information can be retrieved from them. 

# Domain

## Whois

When domain names are registered with ICANN data about who registered it is submitted.
User can make their data private to hide it from the public.
This data can also be false, old, wrong, etc. because there no enforcement of the data provided have to be valid.

The easiest way to view WhoIs information is using the **whois** command on Linux.
other wise site such as [viewdns.info/whois](http://www.viewdns.info/whois).

Because the information can change overtime, which is why historical data lookup could be used to identify a person.

**Historical Whois**:

[whoisology](https://whoisology.com/)

[whoxy](https://www.whoxy.com/)

[domainiq](https://www.domainiq.com/)

Have historical Whois information, it will also try to identify other sites owned by the same person, It does comes with an price.

**Reverse Whois**

It possible to perform reverse lookup on the registrant name that was used.

[ViewDNS reverse WhoIs](https://viewdns.info/reversewhois)

## Hosting

Domains are linked to an IP address. To identify the IP address it point to at the current moment you can use the **nslookup** command, but this will only gain you the current IP address it pointing to. Which is why looking at historical IP information can be used to gain useful information.

Historical domain IP addresses:

[Viewdns iphistory](https://viewdns.info/iphistory/)

[PassiveDNS](https://passivedns.mnemonic.no/)

## DNS

Domain name service are how domain names are translated to IP addresses and back.
It common for multiple domains to be tied to a single IP address, with DNS queries we can find those domains. An domain records contains multiple fields of data that can give us insight.





## Technology

Every website or service is built upon an technology, This is where [BuiltWith](https://builtwith.com/) comes into play, it will try to identify the technology used on the site.

[blacklight privacy inspector](https://themarkup.org/) will look into the website and notify of privacy invasive activity.

When you visit an website you might have notices an icon in the tab bar. This is called an favicon. you are able to find other site which have the same favicon to identify other sites.
Before you start you have you calculate the hash value of the icon this is done with [faviconhash](https://faviconhash.com/).
The next step is to query the hash value on [shodan.io](https://www.shodan.io) using the query **http.favicon.hash:{hash}**




## Domain analytics

In order to track user information when visiting the site. A key is loaded onto the site. That tells the browser to collect data and send it to google. This can be used to find other sites that share the same analytics id.

It common it you own multiple sites to use the same analytic ID to track them all.
This allow us to perform reverse search and pivot from one site to the other sites that also owned by the same user

[Analzeid](https://analyzeid.com/) perform cross-reference of multiple of attributes, like IP, analyst id, etc. To identify other website owned by the same person.

[Spy On Web](https://spyonweb.com/) Is one of the tool that will search an domain name and identify multiple sources of information and tries to cross-reference website that have multiple of the same attributes.
This allow you to identify that possible owned by the same person.

[Domainiq reverse analytics](https://www.domainiq.com/reverse_analytics)
will also perform reverse search on google analytics ID.

[Hacker target reverse analytics search](https://hackertarget.com/reverse-analytics-search/)
Is unique because it also have historical analytics ID.

## SSL certificates

It common for website to have an SSL certificate that allow for secure connection through the HTTPS protocol.

[crt.sh](https://crt.sh)
Identify historical certificates this can allow you to identify other domains that have been registered and with who they where registered with. Where it possible to ask the register for information on the person who register the domain.

[Censys.io](https://search.censys.io/)
Allow you to search on different attribute of certificates, allowing you to pivot on reuse of certificate attribute.
One usecase is to search for certificate which contains an specific name.

The good thing about Censys is that it provided in real-time, ensuring that the data is always up to date.

## Robots.txt

Found at the root of the website, it there to instructions the search engines crawler which webpages should not be index by the search engine.

**e.g. http://www.cnn.com/robots.txt**

This file can help us identify folders of the website like beta sites, websites under development, etc. Which we can possible use to identify additional information.

## backlink

Identify website that link to the target domain. [Host.io](https://host.io) will identify sites that link to the domain

## Redirects

Website can send http code 301 or 302 which tells the browser that the material you are looking for is at a new location. [Host.io](https://host.io) can also help you identify these.

## Monitoring

You might be interested in if an website changes it appears over time. This is where [Visualping.io](https://visualping.io/) can help you monitor websites and notify you if there are any changes to the site.

## Web archive

Record websites in order to preserve websites, allowing one to look back in time to see how the internet have changed over time.

[archive.org wayback machine](https://archive.org/)

[archive.ph](https://archive.ph/)


## Web exploration

Detection of security flaws or forgotten pages, etc. 

[Sn1per](https://github.com/1N3/Sn1per) automate recon tool that can be used to perform attack surface discovery, vulnerability scanning.

[Wig](https://github.com/jekyc/wig) CMS identification tool.

````
python3 wig.py example.com
````


Scan all plugin with know vulnerabilities
````
wpscan --url example.com -e vp --plugins-detection mixed --api-token YOUR_TOKEN
````

[WPscan](https://github.com/wpscanteam/wpscan) Wordpress security scanning tool. Wordpress is one of the most common CMS platform to build you website on. One of the reason it pick is because it easy to setup and there are vast amount of plugins that can help you perform specific tasks.
The problem is then at the security of these plugins is not the greatest and can add vulnerabilities to the site.
What WPscan does it tries to identify what plugins and the version that is running on the site. And uses the WordPress vunerability database to identify if there are any vulnerabilities in the plugins, Wordpress version, site configuration.

default scan
````
wpscan --url example.tld
````


## subdomains

Subdomains are used to organize different sections of an website. There is no limits to the amount of subdomains you can have. There are tools can be used to perform dictionary attack against an site to identify subdomains.