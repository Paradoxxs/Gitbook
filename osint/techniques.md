# Techniques

-- WIP -- Things am not use where to put yet.

### Contact exploitation

By adding the phone number of the target to a clean phone, then installing a social media app, some apps will pair you with target as a contact

The process here is to use a clean phone and adding the phone number of the suspect to the contact list and then installing different social media app such as (telegram, snapchat, tiktok, whatapp, etc) it important the app is allow access to the contact list what will happen is that the phone will happen is that the app will add the person to the application contact list.

Which will give you more data to pivot off.

### Forgot password

Many sites have an second factor for recovery your account. This can be phone number, additional email, etc. 
What you can do is if you know your target have an account on a site and their username or email. 
You can try the *forgotten password* options, some sites might reveals the entire second factor or just an part of the it. 
If you do this on multiple sites you should be able to identify additional information about the target. 

Be aware that this might alert the user that something wrong is going on.

### Trace route

When doing IP geo location on user IP address is can be very difficult to any kind of mening full preciession because the user get assinged a random IP address by DHCP.\
One way to over come this problem is to use traceroute command on the IP in question, using instead the last routing hop and geo locate on that IP address instead, can yield much better results, the reason this work better is because using routing infrastructure will yield more accurate results is because they do not change as much over time.\
One major down fall to this technique is that most routing traffic infasture block IMCP packages, leaving you unable to get the routing IP.

### Identify online ownership

#### WHOIS

Look up who registered the domain, might not be anything useful because of GDPR allow people to hide their information, Alternative there are service that allows you to register IP address anonymously.


### CDN (Cloudflare)

As you try to identify the owner behind websites you are very likely to encounter CloudFlare. Which provide security for website to prevents attack and downtime. They are used to everyone to help provide better service to their customer.

To verify if the domain still resolve at the IP address you can use the curl command,
This will force curl to resolve the website at the defined IP address.

**curl -k {domain} --resolve {domaipin}:{port}:{ip}** 


**SSL certificate** are unique and has it own fingerprint, by looking at historical data you can identify what website have been associcated with the cert.
Censys, shodan, zoomeye and crt.sh  are tools that can be used for this purpose.
The goal is to identify what IP was used when the certificate used.

**Historical DNS reconds** can be used to identify what IP address the domain in the past used to resolve at.

**subdomains** are not always protected by cloudflare, often it only the main domain that is protected, by identifying subdomain you can possible identify other IP address.

**favicon** are picture that is seen in the tab, can be found at example.com/favicon.ico
Each favicon have an unqiue hash, to identify the hash faviconhash.com can be used to calculate the hash
Tools such as sodan.io can be used to search for site with similar favicon or fav-up
sodan.io query :  **http.favicon.hash:{hash}**

**Analytic id** Looking for website that have the same google analytics ID.


## Phishing site path traversal

Phishing sites are often an part of a phishing kit. And by doing path traversal you might be able to access to phishing kit configuration file gaining additional information about the target.