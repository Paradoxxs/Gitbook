

[tiktok api](https://developers.tiktok.com/doc/login-kit-web)

[telegram api](https://core.telegram.org/)

[Viber api](https://developers.viber.com/docs/api/rest-bot-api/)

[line api](https://developers.line.biz/en/)


https://gitlab.com/illwill/skiptracer
testing required




https://github.com/MrTuxx/SocialPwned

# Username

Usernames is how we identify ourself on the internet.
Some people choose to have the same username across multiple platforms allowing one to have an stronger identity on the internet. Other have an new username foreach account they create for privacy purpose making them harder to identify.\
Once you have identify a username you can try and use this information and see if the person reused it across multiple sites.\
Because of the vast amount of sites that exists on the internet. Going through each site manual to identify if the username exist will take too long, for this reason we have to use tools that will automate the process for us. 

## Sherlock 

[Sherlock](https://github.com/sherlock-project/sherlock) python tool that hunts down social media account by username. 

Search for single user.
```
python3 sherlock username
```

Search for multiple users.
```
python3 sherlock username username2 username3
```

## Maigret 

[Maigret](https://github.com/soxoj/maigret) is an fork of sherlock project which also collect information from social media by username. At the current moment is support more then 2500 sites.\


Search for single user.
```
python3 maigret username
```

Search for single user export report as HTML
```
python3 maigret username --html
```


## Userrecon

[UserRecon](https://github.com/issamelferkh/userrecon) find username across 75 social media 

usage:
```
.\userrecon.sh username
```

## Blackbird

[blackbird](https://github.com/p1ngul1n0/blackbird) python tool that will search across 144 sites. 

usage:
```
python3 blackbird.py -u username
```

You can also access the function of blackbird through webserver.\
This command will start blackbird webserver. 

```
python blackbird.py --web
```

If you are not up for running script or using commandline. There also exist sites which will perform the search for you.\
There exists many sites that will perform this kind of search for you. I have selected theses because they provide link to the user profile.

* [instantusername](https://instantusername.com)
* [whatsmyname](https://whatsmyname.app/)
* [usersearch](https://usersearch.org/results_normal.php)

An quick google search will quickly provide you other sites that can perform this kind of service for you. 

# Email

Because of the unique nature of email address it an great search parameter when doing OSINT work.
The good thing about email is that it consists of two parts user and domain part.\
*username@domain.tld*\
First you have the username of the account, try an see if they reused the same name in multiple locations.\
Which can be used to identify new accounts with new information about the target.\
The method of during username searching it provided in the *username* section.

If the email you are trying to identify is using an unique domain name. You can try to use it can be used to try and identify the infrastructure of that domain.\
The *infrastructure mapping* section will provide you information on how to do this.

[epiesos](https://epieos.com/) is an amazing tool when you want to identify the person behind and email address or see what other sites it registered too.\
The way it does this is by using an tool called [holehe](https://github.com/megadose/holehe).\
This tools goes out and try to register or login with that email and see what response it get back. Most sites will tell you if an account with that email is all ready registered.\
It also see if any google or skype profile is resisted using the email and provide you with an link to the profile. Which might contain the real name of the person.

## data breaches

You also have the option to see if the email is part of any breaches or leaks. Using the service [HIBP](https://haveibeenpwned.com/), will allow you to see if the email have appeared in any leaks. If it have you can try to locate this leak and see if it provide any new information about the target.\
Another way is to use data brokers such as [intelx](https://intelx.io/) to see if they have any information about the target.\
More about this processes will be discussed in the *hunt for data* section.


## identify domain mails

If you only have an domain and what to identify emails. There exists services such as [skymem](https://www.skymem.info/) and [hunter](https://hunter.io/). These services have collected email information that you can search through.

Another is to use linkedin to look for account with their work email in the profile use dorks such as:

```
site:linkedin.com domain.tld email
```

## Reputation / Scam

[Emailrep](https://emailrep.io/) Allow you to look up mails and see if they been part of any scams.\
Another service that also allow you to search for email that have been part of an scam is [scamsearch](https://scamsearch.io/).

