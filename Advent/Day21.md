# Malware Analysis - Malhare.exe
> Learn about malware analysis and forensics.

## Task 1: Introduction
- I am asked to only turn on attackbox this time
- I do so and move on to main part

## Task 2: Malware Analysis
- I was given an overview of HTA
- It is a HTML application, which contains HTML, CSS, Javascript and such code
- Unlike normal webpage we can execute it directly on windows
- This makes it exploitable as it can be executed on host machine
- We learn basics of its structure
- Then we learn how to analyse and decode it
- We learn about its basic functions and later try a practical to find info

### Answers:
- The title was between two title tags, `Best Festival Company Developer Survey` (after opening HTA file using `pluma` command)
- `getQuestions` was the function which is downloading survey questions
- `survey.bestfestiivalcompany.com` was inside the above function and contacted
- `ii` was used instead of `i` which is considered typesquatting
- Function had `4` loop in it
- Searched for keyword `trip` in file editor and found answer `South Pole`
- Function `provideFeedback(feedbackString)` had two strings which matched char limit of answer
- Above function contained `/details` endpoint
- `GET` request is used
- `runObject.Run "powershell.exe -nop -w hidden -c " & feedbackString, 0, False` this code is used to execute
- base64 was used to encode
- ROT13 was used
- after solving in cyberchef we get the flag
