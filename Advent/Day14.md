# Containers - DoorDasher's Demise
> Continue your Advent of Cyber journey and learn about container security.

## Task 1: Introduction:
- I was asked to turn on Attackbox and host machine
- I did that and moved on to part 2

## Task 2: Container Security
- At first I was given briefs on what exactly are containers, this part mentioned some common use cases of containers and why they are preferred,  it included subtopics: `installation`, `troubleshooting` and `conflicts`
- A comparision between containers and VM is made
- In a nutshell, a VM runs a completely isolated instance of an OS, whereas containers share host's kernel and only application + dependencies part is isolated
- This is advantageous as it makes it lighter and faster to run unlike VM machines
- Next topic talks about how containers are useful as they can scale faster, as modern applications are not monolith and built on various smaller parts so they can easily be scaled
- A famous engine used for this purpose is `Docker` and it is FOSS too!!
- An important topic is mentioned where it is possible to escape containers and thus gain access to host kernel which can be used to run malicious code on host device
- Now I am supposed to solve challenges and follow their guide

### Answers:
- To list running processes we use `docker ps`
- File named `dockerfile` is used to define instructions to build a docker image
- I followed the commands to gain access to socket and escape the container, thus I went back to root directory and used `cat` to view the flag
