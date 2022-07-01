# Techniques

### Contact exploitation

By adding the phone number of the target to a clean phone, then installing a social media app, some apps will pair you with target as a contact

The process here is to use a clean phone and adding the phone number of the suspect to the contact list and then installing different social media app such as (telegram, snapchat, tiktok, whatapp, etc) it important the app is allow access to the contact list what will happen is that the phone will happen is that the app will add the person to the application contact list.

Which will give you more data to pivot off.

### Trace route

When doing IP geo location on user IP address is can be very difficult to any kind of mening full preciession because the user get assinged a random IP address by DHCP.\
One way to over come this problem is to use traceroute command on the IP in question, using instead the last routing hop and geo locate on that IP address instead, can yield much better results, the reason this work better is because using routing infrastructure will yield more accurate results is because they do not change as much over time.\
One major down fall to this technique is that most routing traffic infasture block IMCP packages, leaving you unable to get the routing IP.

### Identify online ownership

#### WHOIS

Look up who registered the domain, might not be anything useful because of GDPR allow people to hide their information, Alternative there are service that allows you to register IP address anonymously.

### Google search ( Google Dorking)

Google search allows you to search the internet for information. Google allows you to search for file extension locating documents that available to the public.

#### Operators

| Operator  | Meaning                                                                                                                        |
| --------- | ------------------------------------------------------------------------------------------------------------------------------ |
| site:     | Search only on site                                                                                                            |
| filetype: | Search for filetype                                                                                                            |
| cache:    | Google cache of page, it important to add \&strip=1 at the end of the url to ensure only resource from google cache is loaded. |
| inurl:    | search for strings in url                                                                                                      |
| link:     | Find pages that link to the website                                                                                            |
