# Linux CLI - Shells Bells
> Explore the Linux command-line interface and use it to unveil Christmas mysteries.

## Task 1: Introduction
- I was asked to start virtual machine
- So I pressed the start button
- Connected to it using `ssh mcskidy@MACHINE_IP` (where machine IP is the IP address of VM assigned to me)

## Task 2: Linux CLI
- First I was introduced to basic Linux CLI commands
- It included commands such as `cat`, `find`, `cd` and `ls`
- I was also introduced to some common flags such as `-la` for `ls`
- Then I was asked to do some basic challenges on VM
- First one asked me about `ls` and I had to use it with `cat` and `-la` flag to find the challenge's flag
- In second part I had to use find in home directory to find `eggstrike.sh` thus I used `find /home -name *egg*`, then read it using cat
- In third part it asked me about `sudo`
- I was asked to access a user's file using root access so I did `sudo su`, then I was asked to read their bash history to figure out the flag, so I did `cat /root/.bash_history` or we could've just used arrow keys
