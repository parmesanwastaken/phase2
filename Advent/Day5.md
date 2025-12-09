# IDOR - Santa’s Little IDOR
> Learn about IDOR while helping pentest the TrypresentMe website.

## Task 1: Introduction
- I was asked to run the attackbox and host machine
- I did so and went to task 2

## Task 2: IDOR on the shelf
- This part talked about Insecure Direct Object Reference (IDOR)
- This is where few paramters in URL or values in local storage/cookies are changed to gain view access to data that isn't supposed to be accessed by that user
- This is usually because the site doesn't have a authentication check to see whether this usre can see it or not
- It is different from the case where user exploits and gets admin access, which is called vertical privilege escalation. Instead this is horizontal privilege escalation where user can view other data, not designed to e viewed by them
- I was shown an example where I had to login as a normal user and can view children, gifts and vouchers for this
- When I view GET request from networks tab then I can see it asks for userID in GET request header
- We can go to local storage and change this ID by 1 number each time to gain accesss to information regarding children and vouchers of other accounts
- We can also see that some data is stored in MD5 like children's data and this can also be accessed from networks tab
- We can also see voucher IDs and exploit this as they use UUID 1 which is time dependant

### Answers:
- First one asked for IDOR full form which is `Insecure Direct Object Reference`
- Second one asked type of privilege escalation, which is `horizontal` in this case
- Third one was just trial and error to change ID in local storage to gain access and find account which has 10 children, which is `15` in this case
