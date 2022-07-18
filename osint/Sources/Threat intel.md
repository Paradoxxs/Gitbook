# Threat platform

There are many services which will provide threat intelligence, this could be analysis file and website if they are malicious or data breaches broker which stores and index data breaches which you can use to identify new information like password.


# Data breaches

Data providers of information from data breaches and leaks.

## H8mail

[H8mail](https://github.com/khast3x/h8mail) open source password breach hunting tool that will query multiple data leaks brokers sites for information about the target. You have to bring your own keys if you want premium service.

## intelX

[intelX](https://intelx.io/)

Present data It searches in places such as the darknet, document sharing platforms, whois data, public data leaks and others. The free service only give your selective information.

## Breach directory

[Breach directory](https://www.breachdirectory.org/)
Allow through leaks, what makes it difference it provides you with SHA1 hash of the password, which you can crack to identify password.

## leak peek

[leak peek](https://leakpeek.com/)

Service to search in different breaches and leaks, will give you a partial password.

# Threat intel

Service that does data enrichment on the information.

## VisusTotal

[VisusTotal](https:/www.virustotal.com)

probably the most well known threat intel platform, it own and operated by Google and is free to use. What VirtusTotal does that is will scan the file, website, etc. using multiple anti-virus in hope of identifying the content you have provided it is malicious or not.
It will also provide you with information on if similar data have been found in other cases.
It should be noted that everything you upload to the platform can be view and download by everyone that have a paid subscription to the service.

This could example be you have uploaded an malware, what VirusTotal will be is run the file inside an sandbox identify key attributes like IP address used for connects it will then look for other malware that also used the same IP addresses.

## Alienvault

[Alienvault](https://otx.alienvault.com/)
Community driven threat intelligence platform, like with everyone that community driven the information provided might not be 100% accurate. It will try to see if the information have been seen in any intelligence report or incidents. Allow you pivot of new information.

## Hybrid analysis

[Hybrid analysis](https://hybrid-analysis.com/)

Similar to VirusTotal it an Malware analysis service that will try to analyse anything that you upload.

## urlscan

[urlscan.io](https://urlscan.io/)

Scans website to identify if the site perform malicious activity, or try to phish user for credentials.

## Intezer

[Intezer analyze](https://analyze.intezer.com/)

Scans file, url, memory dumps, etc. to see if it can identify if it malicious and any IOC and TTPs used.
Intezer will also try to see if it correlated with any other malware family.



*Threat hunting for adversary C2 and infrastructure*

[Cobalt strike](https://www.shodan.io/search?query=product%3A%22Cobalt+Strike+Beacon%22)

[MSF](https://www.shodan.io/search?query=ssl%3A%22MetasploitSelfSignedCA%22)

[Covenant](https://www.shodan.io/search?query=ssl%3A%E2%80%9DCovenant%E2%80%9D%20http.component%3A%E2%80%9DBlazor%E2%80%9D)

[Mythic](https://www.shodan.io/search?query=ssl%3AMythic+port%3A7443)

[Brute ratel c4](https://www.shodan.io/search?query=http.html_hash%3A-1957161625)

## Greynoise

[Greynoise](https://viz.greynoise.io/) threat enrichment service.

# Malware farm

Services that stores malwares.

## MalwareBazaar

[MalwareBazaar](https://bazaar.abuse.ch/)
The goal of this service is sharing of malware sample with the community. 

## vx-underground

[vx-underground](https://www.vx-underground.org/)
Similar to MalwareBazaar hosting service of malware samples