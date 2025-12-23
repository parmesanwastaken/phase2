# CyberChef - Hoperation Save McSkidy
> The story continues, and the elves mount a rescue and will try to breach the Quantum Fortress's defenses and free McSkidy.

## Task 1: Introduction
- I was asked to turn on AttackBox and Target Machine
- I did so and moved on to task 2

## Task 2: Important Concepts
- I was first told basic difference between encoding and encryption
- It also mentioned how cyberchef was a versatile tool and aided in encoding decoding and performing or reversing variour ciphers
- This part also mentioned how to opne dev tools/inspect web pages

## Task 3: First Lock - Outer Gate
- Basic info on base64, network tab and headers was shared
- And how logic was available to view through debugger tab was shared

### Answers:
- I went to the displayed url
- Then opened another tab of offline cyberchef
- Now I copied username from left panel and decoded it
- Then I checked question from headers in networks tab and encoded it and sent to the panel on left
- This gave me encoded answer so I decoded it and got the password which was encoded too
- So I decoded that and got `Iamsofluffy`
- Then encoded gaurd's username and used that in input field of username

## Task 4: Second Lock - Outer Wall

### Answers:
- This was same as above but the password was again encoded in base64, so decoded it once more
- Password was `Itoldyoutochangeit!`
- Then I again encoded the new username and proceeded to next part

## Task 5: Third Lock - Guard House
- Basics on what exactly is XOR was given
- And how the challenge contained XOR + base64 combo in logic was shared

### Answers:
- First I simply asked `Password Please` as intructed in instructions
- Gaurd took its time and gave me an encoded string
- I reversed it and got encoded password
- Then I followed the logic as mentioned and decoded it using base64 first and then using xor key `cyberchef` as UTF-8
- This gave me the password `BugsBunny`
- Again encoded the guard name and proceeded

## Task 6: Fourth Lock - Inner Castle
- This part gave basics about MD5 hash

### Answers:
- I encoded and asked `Password Please`
- I got a response and decoded it using base64
- This gave me a md5 hash
- I cracked that using CrackStation website
- This gave me the password: `passw0rd1`
- I encoded the gaurd name and proceeded

## Task 7: Fifth Lock - Prison Tower
- This was mix of above challenges

### Answers:
- I encoded `Password Please` and send to guard
- This gave me a base64 string that I decoded
- Then I got another string as password
- According to headers I had 4th recipe
- So I decoded it by first setting ROT13 then Base64 then ROT47
- This gave me the password `51rBr34chBl0ck3r`
- Then I encoded guard name and entered details and it gave me the flag
