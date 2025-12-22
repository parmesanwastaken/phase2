# Web Attack Forensics - Drone Alone
> Explore web attack forensics using Splunk.

## Task 1: Introduction
- I was asked to start the attackbox and host machine
- I did so and went to task 2

## Task 2: Web Attack Forensics
- I am given an overview of Splunk, it stores machine data and we can use advance tools to search and analyse it
- I am given an example command to use which goes through `HTTP` logs to identify malicious activities such as command excecution
```
index=windows_apache_access (cmd.exe OR powershell OR "powershell.exe" OR "Invoke-Expression") | table _time host clientip uri_path uri_query status
```
- We find a base64 string which we can decode and get readable info
- Now we focus on server side errors and Apache error logs using: `index=windows_apache_error ("cmd.exe" OR "powershell" OR "Internal Server Error")`
- Thus we can identify in error logs whether attacker tried to execute a command but failed
- We can explore sysmon (system monitor) to find suspicious activity
- Thus we can use command `index=windows_sysmon ParentImage="*httpd.exe"`
- Now we can identify if Apache spawned processes such as `cmd` or `powershell` which it isn't supposed to
- Attackers often use `whoami` in terminal to check user and thus understand privledges, thus we can use `index=windows_sysmon *cmd.exe* *whoami*` to find such cases
- We can use `index=windows_sysmon Image="*powershell.exe" (CommandLine="*enc*" OR CommandLine="*-EncodedCommand*" OR CommandLine="*Base64*")` to identified base64 encoded queries which are often used by attackers so terms get harder to search

### Answers:
- `whoami.exe` is the first answers, according to the information shared above the challenge
- We can use `index=windows_apache_access (cmd.exe OR powershell OR "powershell.exe" OR "Invoke-Expression") | table _time host clientip uri_path uri_query status`
- After that we can find the answer is `powershell.exe`
