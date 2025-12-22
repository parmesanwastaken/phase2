# Phishing - Phishmas Greetings
> Learn how to spot phishing emails from Malhare's Eggsploit Bunnies sent to TBFC users.

## Task 1: Introduction
- I was asked to start the target machine
- I did that and moved on to task 2

# Task 2: Spotting Phishing Emails
- First I was given overview on what exactly is phishing and motives behind it
- Then the topic switched to how it is different from spam
- Examples for both were presented
- Then social engineering is talked about, and how it is very significant and helps in planning and executing a successful phishing attempt by abusing and manipulating using known knowledge about victim
- Other important things like typesquating and manipulation using similar unicode is used to trick user and get confused with real famous websites
- Advanced methods such as spoofing email because of vulnerabilities is talked about, where authentication fails and and thus spoofing is possible
- Spoofs can be detected by accessing information such as auth results and return path, these are generally attatched with email itself and in real email clients can be viewed in advanced view of email
- Some attacks also send malicious attatchements in body to steal user information and credentials, these are usually accompanied by social engineered info
- Another thing that is mentioned is how phishing isn't just about dropping malware, instead it is carefully crafted to trick users and gain access to sensitive data
- Thus hosting services such as dropbox, google drive etc. are used which can bypass the filers set by email application and make it look more legitimate for an average user which use these on daily basis
- An example of phishing email is provided which uses punycode methods to make phishing domains look similar to actual legitimate domains
- Similarly fake login pages are created on these trick domains which have same/similar interface as actual website and trick users into sharing their credentials
- Attackers also use side channel communication where they move the conversation to an alternate messaging service and continue their social engineering without getting in way of email providers and getting flagged

### Answers:
- First email was spoofing email and made it so it looked like it was sent by Paypal, they faked invoice and created a fake situation of urgency. Selecting these 3 categories gave me the flag
- There was a fake voice message with spoofed email. It categorized it into following to get flag: `Impersonation` `Spoofing` `Malicious Attachment`
- Third flag was given when I cateogrized it into: `Impersonation` `Social Engineering Text` `Sense of Urgency`
- Fourth one was a dropbox link and I got answer by categorizing it into: `Impersonation` `External Sender Domain` `Social Engineering Text`
- Fifth one was `spam` and selecting that gave me the answer
- Sixth one was categorized into: `Impersonation` `Typosquatting/Punycodes` `Social Engineering Text`
