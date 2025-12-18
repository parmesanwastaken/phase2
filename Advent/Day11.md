# XSS - Merry XSSMas
> Learn about types of XSS vulnerabilities and how to prevent them.

## Task 1: Introduction
- I was asked to start the host and Attackbox
- I did the above and went to part 2

## Task 2: Leave the Cookies, Take the Payload
- I am introduced to XSS (Cross site scripting) attack
- In this we learn that we can inject malicious javascript code to get information and run scripts on users
- In reflected XSS where we enter this query in url parameters, this can include simple queries like requesting tokens/cookies to injecting HTML tags such as <script> to run javascript
- In stored XSS, we inject the script on server side itself and thus it runs on every user's device who queries this server, for eg. we can add script tag in some POST query and thus this particular line of code will run on user's device

### Answers:
- First answer is `stored` as we learnt above
- Third answer is `THM{Evil_Stored_Egg}`, we get this flag by doing a simple XSS attack like: `<script>alert('Stored Meow Meow')</script>`
- Second answer is `THM{Evil_Bunny}`, we get this by messing with parameters, first I checked dev tools and confirmed through network queries that search is sent using `/?search=` parameter, so we can do a simple payload by visiting `http://10.48.141.95/?search=<script>alert('test')</script>` and thus we get the flag
