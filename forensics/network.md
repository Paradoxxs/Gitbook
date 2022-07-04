# Network


    Network data flow analysis 
    
Type of data

- Full-packet capture data stores
- Netflow traffic summary
- Infrastructure and endpoint logs


## Aqcusition 

### TLS (HTTPS) Traffic proxy 

Because of the encrypted nature of TLS traffic, if it required by the organization to view this data for forensics purpose, the best way to do this is by setting up a TLS proxy, 
It requires that the endpoint on the network trust the certificate the TLS proxy provides 

Tools
- Squid
- NGINX
- Symantec
- Forcepoint
- Barracuda
- Apache traffic server 

### Port mirror

Will duplicate packet and send a copy out to another specified port. 

### Taps device

Purpose built device which duplicate traffic  and forward the data, with the purpose for monitoring and capture 

### Internet service provider (ISP)
    
One of the problem with many of the network collection method is the amount of the data that is collected, that have to be stored, parsed and analyzed. 

Lack of network design and diagram, are you collecting anything or are there missing evidence because of lack of oversigt. 
And how different solution affect the data that is collected. 
        Encryption, Make it impossible to inspect package content. 
        Cloud and service provider, what data can you aqcuire from the third party. 

### Design

When setting up collection point it important to have when in key location to collect the necessary data to perform forensics investigation. 

# Evidence files

## Pcap

full data packet, because of the size of pcap file it not scalable because of privacy and data volumes reasons
Making it hard to analysis hard amount data.
   
Tools
-Wireshark
-TCPdump

## NetfloW


Summary of data packet. Just the metadata about the packet. The content of the data is not stored.
Netflow is the preferred because of it speed it take to analysis the data, and as more traffic gets encrypted that need to content is decreasing.
Another benefit of not having content is less regulation for privacy.

It should be noted that Netflow only get written to disk when the session has ended, or if the session is longer than 30 min it gets written down and a new netflow artifact is made. 

Analysis
Because of the lack of content it hard to tell if network traffic is C2, exfil or normal traffic.
The best way to analysis Network traffic is looking at the traffic behaviour and matching it with what normal traffic looks like.
https://remnote-user-data.s3.amazonaws.com/x1HJoasKEBaTjg_1t7D1Utrw5iUwzxkxiv8naRKWQNuEnSg80rxKRMj7o3DgN2B374DKesj7Ra1YldccNV-x0vQMRtSHoI7pXlLpmIm7g2Usrvzp7i4FfXXUiATDGG-5.png

### Export 

Because netflow export uses UDP which is not a reliable or guaranteed protocol, and each export packet lost is 30 netflow/evidence. 

### Tools 

System for internet-level knowledge (SiLK) - Collection and analysis tool, design for big enterprise system.  

nfcapd  - Tactical capture for small to mid size, long-term collection 
            nfpcapd - Convert pcap to netflow for nfcapd

## Logs

Artifacts of what happened, because there no standard format for logging it have to be parsed and analyzed. 


Protocols
    HTTP
        Overview
            ASCII-based stateless protocol using port 80 for communication, which can be used in a varity of way: document, raw daa, media, api, etc. 
            Forensics wise it allow for analysing user activity during web browsing. 
        Version
            HTTP/1.1:1997 (most common today)
            HTTP/2:2015 (binary, multiplexed, generally with TLS)
                Fully multiplexed allow for multiple requests per packet, Compressed headers in tags. Also allow server to force push objects to the browsers without it having it been requested. 
            
        Design
            HTTP/1.1 
                Header 
                    Request
                        https://remnote-user-data.s3.amazonaws.com/RYloS0MpQoA_8382CLkVkKqKy16nt3CBnVs8IgdIF8VKwX2ESAxkBQxJTBqGwFs4b_u7XXL7G7kxxLLFcAwXs-nK0g7RG9PYpjJ13IwG1O5aQLDu7W5XVFbJ90-MPrMH.png 
                        Most of field in the header are optional 
                    Response
                        https://remnote-user-data.s3.amazonaws.com/uVVSf0vfI85YLghkFYRRdWmGkQiaT_NmgtOItvmfmJ01H09uBUgY114eoKft4W3BldMUridlqUrpUfxe5P4Go8AujTEF2Cra0FL5UxIrWpY0i0XRVXZz_HuPo6oN3T-I.png 
                    Content 
                        Can be part of both request and response, the format of the content can be anything, 
Client can define the format it accept in it request header. 
            Logs
                Format
                    NCSA common format
                        https://remnote-user-data.s3.amazonaws.com/HSVW_o03n0MCx3RX3fpgxFtYuhwIvkyA_dTeHrQsR-_4uGzDQBddGP5TKaxyXJflCx4PH8vXUF_QR3wpKq2DgzLH5YXTMKggfBh2aGBNwLwIyDtaXLHD1hzexlttr3st.png 
                    W3C Extended format
                        https://remnote-user-data.s3.amazonaws.com/iSzftzAwmyHOGX6vfbQX9Orrkj0y8Q0BP9VT-oDuWh-UfR9D2OR3802FYiyj-Yfv-60aaZwnJDR8sgS29OajUyWH6xon7C3m1nmBGcnG23cpoXAWZ8Wf0nrlxoTg9Vnd.png 
                    IIS log file 
                        https://remnote-user-data.s3.amazonaws.com/Be8U__8Fv-1cuZwvC6FnyB1nvchrr-SR0PtN5YDcxx7PYYHS6EhTRpj9aqkWAsXvHT4WyIFg-vacQN__DV6iz_SIepJ4AHF0wIPAd8WWNO2oeSjkSuctMtmFfyj8zCuV.png 
            Resource
                List of HTTP header fields - Wikipedia 
    DNS 
    SMB


Analysis Network 
    statistics analysis
        Because of the amount of data that needs to be analyzed in network forensics an good starting point is using statistics to get an idea of how the data is layout, 
One way of doing this is to plot the data onto a graph to visual the data and look for outliner in the data set. 
frequency analysis to see if some packets appear more often then expected. 
This is just some of the statistics method that can be used to understand the data, and identify what packets that needs to be examined more closely. 
        Data driven analysis
            Very similar to statistics analysis  
    Expected protocol and connection 
        Map out the protocol and connection that you expect from the network 
            e.g. https://remnote-user-data.s3.amazonaws.com/ISJTIsCmlagnM9tZXv0nT8rnOCWm_HdJ3oPJOFWKAWwgWacUsjdIwcGHX7H-eIPrHCDjqDuneeDPk8GvlEfrMBPVidpVpN-Qvfiyn6I2BYSPI_JlIHn6V4BabnzU3rJO.png 
    Encryption
        As encryption become more common content to become more irrelevant, which it way it have to be correlated with data on the endpoint. 
And malware reverse engineering can yield great insight. 
    Mapping 
        Time to live (TTL)
            By pinging a server like a mail server, you can use the response to calculate the layers of the organisation network 
            e.g. you ping a server can get a response back that have TTL of 61, we know that OS like to use round machine numbers (32,64,etc), then by calculate the difference between the response TTL and closet machine number we can get an idea of the network layers 
Packet decoding 
    Lenght : When calulating length of a packet is always multiplied by 4 to the value in length field e.g. IP header start with 45, 4 tells that is ip version 4 and 5 say the header have a lenght of 20 (5*4)  
    Offset : When offset field is calulated is multiplied by 

Protocol reverse engineering
    Overview
        Process of extracting structure, attributes and data from network protocol 
        Purpose to generate network based IOC, and develop decoder to identify the activity. 
    Attribute
        Structure
        Flow
        Encapsulation
        Functionality
        Encoding and encryption routines
    Data source
        Client/server binary or source code
        Captured network traffic
    Approaching
        Define what you are trying to achieve
        
