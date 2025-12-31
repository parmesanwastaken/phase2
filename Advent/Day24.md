# Exploitation with cURL - Hoperation Eggsploit
> The evil Easter bunnies operate a web control panel that holds the wormhole open. Using cURL, identify the endpoints, send the required requests, and shut the wormhole once and for all.

## Task 1: Introduction
- I am asked to start the Attackbox and target machine
- I do so and move on to task 2

## Task 2: Web Hacking Using cURL
- I am taught what basic things `curl` command does
- I am supposed to first use curl with the provided IP are parameter, this sends a `HTTP GET` request
- Then I am asked to send a `POST` request using command `curl -X POST -d "username=user&password=user" http://10.49.138.162/post.php`
- For additional fields we can use `curl -X POST -d "username=user&password=user&submit=Login" http://10.49.138.162/post.php`
- We can add a `-i` flag to see what exactly server responds with
- We can also use curl to save and use cookies
- We can also bruteforce using a wordlist
- Useragents can be changed/spoofed using `-A` flag

### Answers:
- This was just basics and using command `curl -X POST -d "username=admin&password=admin" http://10.49.138.162/post.php` I got the flag
- Using `curl -c cookies.txt -d "username=admin&password=admin" http://10.49.138.162/cookie.php` first then using `curl -b cookies.txt -d "username=admin&password=admin" http://10.49.138.162/cookie.php` gives us the flag
- We follow the steps earlier and create a wordlist using `nano passwords.txt` then we use create a bash script that sends curl requests in loop
- Thus when we run this script we recieve the password `secretpass`
- We can use `curl -A TBFC  http://10.49.138.162/agent.php` and thus get the flag

## Task 3: Conclusion
- The AI generated lore finally ended
- I can finally get rid of seeing AI art!!!
