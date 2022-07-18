---
description: Are hidden network which requires special tools to access .e.g TOR
---

# What is the dark web

### Freenet&#x20;

Distribution of file sharing, small userbase

When content is uploaded, it is broken into pieces and distributed across the nodes, Uploading a file will provided a key, anyone that want to retrievere the information must provide the key.

Browsing freenet involves requesting files from the data store and viewing them locally, There can be a high latency with request for data because they have to be assembled from multiple source, The long your node is online and the more space you give it, the faster the speed will be because more data will be stored locally.

Modes

* Low security
  * Opennet connects to random peers, It less secure because you do not know who those peer are.
* High Security
  * Darknet mode will only connect to nodes that you have specified. It more secure because you know the node you are sharing data with.

Keys

* Content hash keys (CHK) : file
* Signed subspace keys (SSK) : web site
* Updatable subspace keys (USK) : version of sites
* Keyword signed keys (KSK)

Tool

* Freenetproject.org

### The invisible internet project (I2P) -&#x20;

Anonymity and security for communications, Medium user base.

The main purpose of I2P is to protect communication from eavesdropping, monitoring and traffic analysis, This is done by using one way tunnel that are temporal tunnels.

Traffic flows from outbound tunnels across multiple hops to inbound tunnel, it is then consumed and rerouted or used.

* ![](https://remnote-user-data.s3.amazonaws.com/o39pzYPzzjUcKv4Ck7l3pCcC4agyRKl1f0q5IFnXfZhKT7ELpNNWhQeLk-o7E2-j0W0AQQk4CWtFd7ll0O8wLXirexL9AEe\_diqh9poQKI84EZc7aeRn5E7sddlFq4CW.png)

I2P uses a hosts.txt or Block file binary naming service for translation. Other users hosts files are periodically merged with yours. Users configure subscriptions to other hosts files or address books for regular mering. Thes actions increase the number of sites and nodes your computer knows.

Tools

* geti2p.net

### Tor

Anonymity and bypassing restrictions, Large userbase.

The onion routing project, main purpose is to protect how your data gets from your system to the destination and interfere with or defeat censorship, network blocking and monitoring. Users chooses a path with a set of nodes and negotiate a virtual circuit path through the network, in which each node only knows its predecessor and successor, and no others. As traffic flow down the circuit it is unwrapped by a symmetric key at each node, which reveals the next node.

Tor uses the .onion Top level domain

By adding .ly at the end allow you to access tor site outside the TOR network, very useful for scarping website



Steps taken to secure the network

* The source picks the path the data travel
* Each relay decrypt the outer layer and forwards the content to the next node
* The payload remains encrypted until it reaches the destination



Caution when using Tor

* Careful using files download from Tor
* HTTP when possible
* Stay in the dark web when using hidden services
* Do not use personal information
* Avid using internet sites that requires authentication from Tor

Risk when visiting sites.

* Malicious files
* Revealing information
* &#x20;Attacks against the browser and computer system
* Illegal material


## Dark web threat hunting

A large amount of useful intelligence can be gained from the darkweb, such as malware and vulnerabilities for sale. uncovering planned cyberattack on private forums. This is where HUMINT collector can be used to interact with the threat actor to gain additional information such as undiscovered attack through data sales. Indication of future attacks through bragging of access to network, etc.

### Law enforcement operations

Law enforcement officers can infiltrate private sites, forums, and marketplaces in order to collect evidence which would be used in the case of legal prosecution against individuals involved in illegal activity.

