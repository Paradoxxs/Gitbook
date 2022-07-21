# Building threat profile

This section will be about building an threat actor profile matrix.\
Which is an excel sheet with all the accounts, username and all other personal information related to the actor. You can start with these three tabs.
* Accounts
* Verifications
* Dumps
  
Accounts is used to identify how email and account is connected to each other.\
Verifications track password rest and verification question information.\
And Dumps is data from leak and breaches.

Before I start you are properly wondering what are *password reset information*.\
When you click the *Forgot password* option on website you are prompted to verify your identity.\
E.g. An simple example of this is when website say they have sent an reset email to *a*******@gmail.com. Other times you can select from multiple options. Such as SMS, answering security questions, and etc.\
This information can be critical when building an profile of an person. 

e.g. Verficiation header
|Site|Email|username|Email|number|
|---|---|---|---|---|


When yo are ready to start the investigation, I personally start with where the threat actors are. Hacker forums and see if you can identify any information on your target from way.\
lets say you are looking for an threat actor names *ACE99*. What you can do is using the *insite:* operator to search for username on these forums.


Here I will be searching for the username within the site breached.to
````
ACE99 insite:breached.to
````

If you see that account have been banned you might be lucky that the site have a ban list. Which list out every user that have been banned and the email address used to register the account.\

