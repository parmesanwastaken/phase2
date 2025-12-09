# Malware Analysis - Egg-xecutable
> Discover some common tooling for malware analysis within a sandbox environment.

## Task 1: Introduction
- I was given a basic lore thingy and asked to start the host machine
- I read through it and started the machine, adn continued to task 2

## Task 2: Malware Analysis Using Sandboxes
- First I was given basics on sandboxes i.e they are isolated environments used to run and look through malware
- Then I was taught about static analysis which gives us more info on malware, we can use `checksum` hashes to find whether this particular file was previously found somewhere or not (especially useful on sites like virustotal who kinda store db/s of these analysis)
- Other parts of static analysis include strings, imports and resources, which can further be uses to know more about files
- Now I was asked to actually dissect malware and see stuff using `PeStudio`
- First I was shown an example and later asked to perform it on `HopHelper.exe`
- I was then asked to analyse strings, which contains IP addresses, URLs etc. This was last part of static analysis
- Now in actual analysis I was taught to use Regshot which took snapshot of registry before and after running malware in sandbox
- They mentioned how lot of malwares startup on boot by adding `Run` key in registry
- Now I am introduced to ProcMon i.e Process Monitor, it basically shows how different processes interact with Windows and extensively shows us what exactly each process is doing
- We can capture these processes and later filter them to find useful information

### Answers:
- The first one asked for checksum hash, i.e SHA256SUM value of `HopHelper.exe` so I opened it in PEstudio and copied `F29C270068F865EF4A747E2683BFA07667BF64E768B38FBB9A2750A3D879CA33`, which was the answer
- Second part asked me to find flag in strings tab, so I sorted it alphabtically and found `THM{STRINGS_FOUND}`
- For third part I created a registry snapshot before running the executable and another after running and then got registry value when I compared them and searched for `RUN` : `HKU\S-1-5-21-1966530601-3185510712-10604624-1008\Software\Microsoft\Windows\CurrentVersion\Run\HopHelper`
- I ran the program then ran `HopHelper.exe` and then paused the capture, then I filtered for `TCP` by going to `Operation > contains > TCP > add` then I selected process to be `HopHelper.exe`, now I opened the captured data and could see it uses `http`
