---
description: Tool and techniques related to the dark web.
---


## Onionscan

[Onion Scan](https://github.com/s-rah/onionscan) is a dark web investigation tool
The goal of onion scan is to help research and investigation monitor and track TOR sites. and the second function is identify security issues within their service. e.g. misconfiguration.

Verbose output from the scanning

````
onionscan --verbose site.onion
````

You can also have it create a json report for you.
````
onionscan --jsonReport site.onion
````
## TorBot

[Torbot](https://github.com/DedSecInside/TorBot) Onion crawler


## Onioff

[OniOFF](https://github.com/k4m4/onioff) is an onion URL inspector.

Take an list of onion sites, does URL inspection and output it to an txt file.

```
python onioff.py -f onions.txt -o report.txt
```
