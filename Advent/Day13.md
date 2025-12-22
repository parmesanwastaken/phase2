# YARA Rules - YARA mean one!
> Learn how YARA rules can be used to detect anomalies.

## Task 1: Introduction
- I was asked to start the VM
- I did that and finished part 1 and moved on to second part

## Task 2: Yara Rules
- First a little bit of lore from their AI generated story was shared lol
- Then it talked about what exactly is YARA and how it gives the user choices and allows them to define their own rules
- Then general reasons and use cases of YARA were shared and how it differentiates itself from other tools
- Several advantges of YARA were shared which included how it is speedy and efficient and main thing that it allows user to define their own rules to fight back and analyse malware instead of relying on antivirus softwares and other means of updates
- `Metadata`, `Strings` and `Conditions` are used to define YARA rules, an example was shared and how to dissect it to understand what the json looking code did
- Topic `Strings` was was explored which included subtypes such as `text strings`, `hexadecimal strings` and `regular expression strings`
- They went further deep into these subtopics and gave a brief on them or their further smaller types which helps us detect common bypasses that are usually used by attackers to bypass protections
- Now the `Conditions` part was explored
- This helps us define specific cases such as trigger when a specific string is found or write `any of them` to trigger for multiple strings
- We can even use logic operators such as `and` , `or` and `not` to set specific conditions
- Even filesize, entrypoint, or hash can be used as YARA can scan even properties and not just contents
- An example of YARA code is shown with instructions to how to write a basic CLI command to execute this

### Answers:
- I created a YARA file using `nano test.yar` and added following rules:
```
rule TBFC_string
{
        strings:
                $TBFC = "TBFC"
        condition:
                all of them
}
```
- This showed 5 file paths for images, thus the answer was `5`
- Second answer was regex `/TBFC:[A-Za-z0-9]+/`
- The only weird file was `embeds` so I did `cat ./Downloads/easter/embeds` and it had answers `Find me in HopSec Island`
