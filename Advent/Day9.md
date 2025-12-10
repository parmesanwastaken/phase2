# Passwords - A Cracking Christmas
> Learn how to crack password-based encrypted files.

## Task 1: Introduction
- I was asked to turn on the host machine
- I did this and went to task 2

## Task 2: Attacks Against Encrypted Files
- Different types of attacks are introduced which can be used to crack weak passwords
- Dictionary attack bruteforces the hash or password using wordlists
- Mask attacks use actual brute force method where it tries every possible method to find the password

### Answers:
- We can simply use `pdf2john Desktop/flag.pdf > hash1.txt` to get the hash from PDF
- Now we can use wordlist to crack the password and open the pdf, thus we use `john --wordlist=/usr/share/wordlists/rockyou.txt hash1.txt`
- This gives us the password `naughtylist` which we can enter while opening the pdf and get the first flag
- Similar for zip we use same commands but with `zip2john` to get the hash and thus get the password `winter4ever`
- We can use this to extract the zip and get the flag
