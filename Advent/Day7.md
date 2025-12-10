# Network Discovery - Scan-ta Clause
> Discover how to scan network ports and uncover what is hidden behind them.

## Task 1: Introduction
- I was first asked to start the attackbox and the host machine
- I did this step and moved to part 2

## Task 2: Discover Network Services
- I was first asked to go through network basics on other page, so I first did that
- Now I was told about who the host is and their IP address and my goal to scan open ports and exploit them
- I was asked to use nmap for this particular task
- I was asked to generate the report using command `nmap 10.48.190.128`
- I found 2 open ports, 22 (tcp) and 80 (http)
- Thus we can either access the website using http prefix or connect using SSH (but we need password)
- We can get more verbose output and scan all port using `nmap -p- --script=banner 10.48.190.128`
- This will give us more detail on what's behind the ports and total open ports (not the most common ones like before)
- Turns out FTP is running on port `21212` instead of default `21` and some TBFC application on `25251 `, we can access ftp using `ftp 10.48.190.128 21212`
- Now we connect to the application using netcat, here we will find second key
- We learn we can scan in UDP using nmap by using `-sU` flag, thus we find open port `53` using this which is related to DNS
- Now we can enter the whole flag on website to gain admin access
- Now that we have access to the server we can simply see all ports using `ss -tunlp`
- Thus we can query sql using this too

### Answers:
- We can get first answer by visiting `http://10.48.190.128` and copying the text on top of website which says `Pwned by HopSec`
- For second part we can simply find first key by accessing ftp through nmap and using `get tbfc_qa_key1 -`
- For third part we can find second key by connecting to application using `nc` and then using `HELP` command and thus getting key using `GET KEY`
- For 4th part we need to find third key which we can by querying dns with command `dig @10.48.190.128 TXT key3.tbfc.local +short`
- For 5th part we know default SQL port is `3306`
- We can find flag from terminal on website using `mysql -D tbfcqa01 -e "select * from flags;"`
