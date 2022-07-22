# Analysis


## Sources

There are many places that have categories different tool based on the information you can use to gather additional information to pivot off.
Here is my own tool https://paradoxxs.github.io/mindmap/ that maps out different source of information both forensics and OSINT.

### Pivoting

Is the art of going from one piece of data to another one.


# Automation

## SpiderFoot

[Spiderfoot](https://github.com/smicallef/spiderfoot?ref=d) is an open source OSINT automation tool, integrates with multiple data sources for analysis. You can on the Github page see the data source it can connect with, some of them require an API key to gain intel from.

It an complete solution which allow for both data collection and analysis.
Automating the frequently performed OSINT processes ensuring that it done the same way everytime.
Has a web-interface for easy use for both collection and visualizations of the data

Spiderfoot also have a commercial tool called SpiderFoot HX, which is a cloud based solution. Which means when you go out to query sites for information it will be from SpiderFoot address instead of yours.  

## ReconNg

[Recon-ng](https://github.com/lanmaster53/recon-ng) open source commandline tool. Reconnaissance framework allows you to quickly perform OSINT. Built with the same mindset as Metasploit.
Recon-ng uses SQlite database(s) to store it data. The workspace function will separate the data from different cases from each other by creating an new database for each workspace.
 

Recon-ng features is split into small components called module where each module perform one specific task.
Per default it comes with zero modules preinstalled, it up to you to install the required module needed to perform you task.
The reason for this is because many of the modules requires API to retrieve information. To ensure user does not get error messages when running modules which they do not have API keys for. They choose to have no pre-installed modules.


````
marketplace search
````
Will display every module and the current status.

If you do not want to go trough the process of selecting and just want to install all the module. The following command will install everything.

````
marketplace install all
````

Recon-ng uses google analytics to identify which modules are the commonly used. The reason for this is to identify which modules needs the most focus support wise.
To turn off this features lunch the no analytics flag.

````
recon-ng --no-analytics
````

Recon-ng will perform a lot of web request, if you want to hide that the request are coming from Recon-ng to need to change the default user agent, which is *Recon-ng/v5*.
