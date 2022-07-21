# IP address

Internet protocol (IP) purpose is to handle transmissions of packets between network end point, Host identify with a unique address. Using the OSI layer 3.

IP is a unique number that that reference to a computer.
IPv4 is a 32-bit limit to 4.294.967.296, because of this limit NAT have been developed to allowing more computers on the internet.
IPv6 is a 128-bit where the limit is 3.4 x 10↑34

When it comes to analysis IP addresses. I quickly go to [ipinfo](https://ipinfo.io/) because it can identify a lot of information. If you prefer to use cli they also have they option [ipinfo cli](https://github.com/ipinfo/cli).


Another useful service is [ipinfodb](https://www.ipinfodb.com/) which also tries to geolocate IP addresses and perform service figerprinting.
## WhoIs

IP are registered like domains and using the **WhoIs** command will allow you to view the current WhoIs information.

[domainiq](https://www.domainiq.com/)

[ViewDNS](https://viewdns.info/whois/)

[ipinfo](https://ipinfo.io/) or [ipinfo cli](https://github.com/ipinfo/cli)

Does everything from identifying location, VPN, Service, domains and etc.

## Reverse domain names lookup
Multiple domain names can be hosted on a single IP address, using reverse dns lookup allow you to identify every domain hosted on the IP.

[View DNS Reverse IP](https://viewdns.info/reverseip/)

Bing search engine can also be used to identify domains hosted on a ip address. Using the query parameter **IP:{ip address}**.

[ipinfo](https://ipinfo.io/)

Does a everything from identifying location, VPN, Service, domains and etc.

[bing.com/search?q=ip%3a+204.93.177.100](https://www.bing.com/search?q=ip%3a+204.93.177.100)

Will only identify one domain, if multiple domain are hosted on the same IP use the tools above.

````cmd
nslookup {ip address}
````

## IP location
It possible to cross-locate an IP address.
Most often when searching for IP location it the providers location that is provided.

[ipinfo](https://ipinfo.io/) or [ipinfo cli](https://github.com/ipinfo/cli)

[ipinfodb](https://www.ipinfodb.com/)

[Geo-Recon tool](https://github.com/radioactivetobi/geo-recon)

[db-ip](https://db-ip.com/)

[iplocation](https://www.iplocation.net/)

[maxmind geoip](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data?lang=en)

Database over IP addresses geolocation.

## IP classification

Lookup up IP address that is involved in fraud and scams.

[Scamalytics](https://scamalytics.com/ip)

Will try to score IP address based on their risk.

[getipintel](https://getipintel.net/)

Using mathematical and computing techniques to identify is the IP is used as VPN or TOR node. Because the result is normalized it range is from 0 to 1. There 1 indicates it a VPN or TOR node.

[ipinfo](https://ipinfo.io/) or [ipinfo cli](https://github.com/ipinfo/cli)

## Ports

Every service that is hosted on a IP address need it own port, one of the most common ports are HTTP (80) and HTTPS (443). There might be additional ports available.

## Censys

[Censys](https://search.censys.io/)

Will allow you to search on IP addresses providing you with what ports are open on the individual ports.

## Shodan

[Shodan.io](https://www.shodan.io/) is another option which scans the internet looking devices and try to fingerprint the service is running on the port. When it comes to IP address we can use it to identify the service and version that are running on the IP.


## Namp

-WIP- should this be part of the book?

Nmap is a Port Scanner tool, used to discovery open ports, services version and OS fingerprinting

Nmap scripting engine allows for [[Vulnerability Scanning]] for the most common Vulnerability  
Scanning of [[IPv6]] is support  but limited to a single address. 
	- OS fingerprinting, NSE scripts, SYN or connect scans and ping scan. 

### Script
--script
`--script==vuln`  activate all script in vuln category
-   `safe`:- Won't affect the target
-   `intrusive`:- Not safe: likely to affect the target  

-   `vuln`:- Scan for vulnerabilities
-   `exploit`:- Attempt to exploit a vulnerability
-   `auth`:- Attempt to bypass authentication for running services (e.g. Log into an FTP server anonymously)
-   `brute`:- Attempt to bruteforce credentials for running services
-   `discovery`:- Attempt to query running services for further information about the network (e.g. query an SNMP server).
-   
### Usage

|switch|description|
|---|---|
|-A|Agressive mode|
|-sV| version|
|-sT| tcp connect scans|
| -sS| TCP SYN scans|
|-sN| TCP null scans|
|-sF| TCP FIN scans|
|-sX| TCP xmas scans|
|-o| operation system|
|-O| Output|
|-oN| normal output|
|-oG| grabable output|
|-v| Verbose|
|-vv| Very verbose|
| --reason| reason |
|-sU| udp |
|-p-| all ports|
|-p ##| scan port|
|-p ##-##| port range|
|-T|Level of aggression from 1 to 5|


	
 Nmap cheat sheet: 
  - https://www.stationx.net/nmap-cheat-sheet/

https://nmap.org/nsedoc/


## Torrenting

Identify what illegal material that have by download on a specific IP address.

[I know what you download](https://iknowwhatyoudownload.com/)


## TOR nodes

The onion router relay nodes used to hide people identify.

[Tor porject metrics](https://metrics.torproject.org/exonerator.html)

Will tell you if an specific IP address was used as a TOR relay.

[ipinfo](https://ipinfo.io/)

Does everything from identifying location, VPN, Service, domains and etc.