# Obfuscation - The Egg Shell File
> McSkidy keeps her focus on a particular alert that caught her interest: an email posing as northpole-hr.

## Task 1: Introduction
- I am asked to start the Target Machine
- I did so and moved onto second part

## Task 2: Obfuscation & Deobfuscation
- I am introduced to what exactly is obfuscation and how it is used by attackers to bypass hardcoded rules
- Real world example of `XOR` cipher is given and steps to obfuscate one ourselves is showed using cyberchef
- Then basics of deobfuscation are shown, that how we can undo common ciphers and info we require to do so
- If we are unsure we can use magic option in cyberchef, which tries multiple methods to deobfuscate
- Attackers often use layered methods so methods such as `magic` become harder to use as the combinations increase

### Answers:
- I decoded the base64 string and replaced it in script to get the first flag
- I XOR'd the input with key given in script and replaced in script and ran to get the flag
