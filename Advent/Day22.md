# C2 Detection - Command & Carol
> Explore how to analyze a large PCAP and extract valuable information.

## Task 1: Introduction
- I was asked to turn on the Target Machine
- I turned it on and moved to task 2

## Task 2: Detecting C2 with RITA
- I am given a brief on RITA
- It analyzes network traffic captures and logs to detect command and control communication
- Benefits and features of RITA are mentioned
- RITA only accepts input as zeek logs so we use that
- Zeek can also convert PCAPs to structured logs, so we can use that for aiding us
- We can use `zeek readpcap` and read it through `cat` command
- For analyses we can use RITA through `rita view` (kinda gives a gui in terminal)
- We can use search bar through `/` and get help by `?`
- Basics on different panes are provided in guide
- Now we do the practical on `~/pcaps/rita_challenge.pcap`

### Answers:
- I use `zeek readpcap`
- Then I imported it in daatabase `test`
- I used `rita view test` to read it
- Counted manually and answer is `6`
- The tab on right side mentioned `prevalence`
- Checked manually and highest was `40`
- We can use `dst:rabbithole.malhare.net beacon:>=70 sort:duration-desc` in search
- According to right pane answer is `80` port
