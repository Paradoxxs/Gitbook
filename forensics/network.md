---
description: Network data flow analysis
---

# Network

## Network

Type of data

* Full-packet capture data stores
* Netflow traffic summary
* Infrastructure and endpoint logs

### Acquisition

#### TLS (HTTPS) Traffic proxy

Because of the encrypted nature of TLS traffic, if it required by the organization to view this data for forensics purpose, the best way to do this is by setting up a TLS proxy, It requires that the endpoint on the network trust the certificate the TLS proxy provides

Tools

* Squid
* NGINX
* Symantec
* Forcepoint
* Barracuda
* Apache traffic server

#### Port mirror

Will duplicate packet and send a copy out to another specified port.

#### Taps device

Purpose built device which duplicate traffic and forward the data, with the purpose for monitoring and capture

#### Internet service provider (ISP)

One of the problem with many of the network collection method is the amount of the data that is collected, that have to be stored, parsed and analyzed.

Lack of network design and diagram, are you collecting anything or are there missing evidence because of lack of oversigt. And how different solution affect the data that is collected. Encryption, Make it impossible to inspect package content. Cloud and service provider, what data can you aqcuire from the third party.

#### Design

When setting up collection point it important to have when in key location to collect the necessary data to perform forensics investigation.

## Evidence files

### Pcap

full data packet, because of the size of pcap file it not scalable because of privacy and data volumes reasons Making it hard to analysis hard amount data.

Tools -Wireshark -TCPdump

### Netflow

Summary of data packet. Just the metadata about the packet. The content of the data is not stored. Netflow is the preferred because of it speed it take to analysis the data, and as more traffic gets encrypted that need to content is decreasing. Another benefit of not having content is less regulation for privacy.

It should be noted that Netflow only get written to disk when the session has ended, or if the session is longer than 30 min it gets written down and a new netflow artifact is made.

Analysis Because of the lack of content it hard to tell if network traffic is C2, exfil or normal traffic. The best way to analysis Network traffic is looking at the traffic behaviour and matching it with what normal traffic looks like.&#x20;

| Protocol | Client volume | Server colume | Connection duration | Potential activity    |
| -------- | ------------- | ------------- | ------------------- | --------------------- |
| HTTP     | Small         | Large         | Short               | Typical http download |
| HTTPS    | Large         | Small         | Various             | HTTP post upload      |
| HTTP     | Large         | Large         | Long                | TLS VPN               |
| SSH      | Small         | Large         | Various             | SCP download          |
| SSH      | Various       | Various       | Long                | Command shell         |
| DNS      | Large         | Large         | Long                | Tunnel?               |

#### Tools

System for internet-level knowledge (SiLK) - Collection and analysis tool, design for big enterprise system.

nfcapd - Tactical capture for small to mid size, long-term collection nfpcapd - Convert pcap to netflow for nfcapd

### Logs

Artifacts of what happened, because there is no standard format for logging it have to be parsed and analyzed.




# Analysis Network

## Statistics analysis
 Because of the amount of data that needs to be analyzed in network forensics an good starting point is using statistics to get an idea of how the data is layout, One way of doing this is to plot the data onto a graph to visual the data and look for outliner in the data set. frequency analysis to see if some packets appear more often then expected. This is just some of the statistics method that can be used to understand the data, and identify what packets that needs to be examined more closely. Data driven analysis Very similar to statistics analysis\

## Expected protocol and connection

Map out the protocol and connection that you expect from the network. Create an filter which will filter out the known good network connection. You then go through the rest of the network and start categoring it as good or bad.

## Encryption

As encryption become more common. Getting the content of the packet have become less possible, which it way it have to be correlated with data on the endpoint. And malware reverse engineering can yield great insight.
  
## Mapping uisng Time to live (TTL)

This is done by pinging a server like a mail server, you can use the response to calculate the layers of the organisation network e.g. you ping a server can get a response back that have TTL of 61, we know that OS like to use round machine numbers (32,64,etc), then by calculate the difference between the response TTL and closet machine number we can get an idea of the network layers.



## Protocol reverse engineering

Process of extracting structure, attributes and data from network protocol Purpose to generate network based IOC, and develop decoder to identify the activity.
Start by looking at the network attributes and 

Network attribute
- Structure
- Flow Encapsulation
- Functionality
- Encoding and encryption
- routines


## WIFi

|Term|Explanation|
|---|---|
|SSID|Service set identifier, name of the wirelress network|
|BSSID| Basic service set identifier, unique ID of wireless transmitter|
|beacon| Announcement from access points broadcasting SSID|
|probe request| Announcement from client requesting a specific SSID|