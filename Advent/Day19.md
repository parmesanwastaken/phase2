# ICS/Modbus - Claus for Concern
> Learn to identify and exploit weaknesses in ICS systems.

## Task 1: Introduction
- I was asked to start the attack box and and target machine
- I did so and moved to part 2

## Task 2: SCADA (Supervisory Control and Data Acquisition)
- I am given an overview of SCADA
- I am then given a brief on SCADA system and also there was kinda an analogy of it being like nervous system and acts as a bridge between human operator and machines
- An example of usage of SCADA system in drone delivery system is mentioned
- Then the main part comes on why they are targetted

### Answers:
- It was mentioned port of modbus is 502 over TCP

## Task 3: PLC & Modbus Protocol
- I am given a brief on PLC, basically they are programmable machines
- Then I am told briefly about Modbus and it mentions that it is a communication protocol used by machines to talk to each other
- Datatypes of modbus are mentioned
- Another topic about how modbus is addressed is shown with plenty examples
- Then smaller topics are glanced over which put together helps us connect the dots and figure out how to exploit

## Task 4: Practical
- We are given a guide and asked to use tools such as `nmap` and `pymodbus`

### Answers:
- We use `nmap` to scan important ports using: `nmap -sV -p 22,80,502 MACHINE_IP`
- We find http cctv camera service on port 80 and modbus on tcp 502
- Read through step 1-5 (as instructed)
- We create a new script using `nano` and paste the code as given in guide
- After reading the output, we make following changes:
```

    Disable protection mechanism (C11) FIRST
    Change package type to Christmas gifts (HR0 = 0)
    Enable inventory verification (C10 = True)
    Enable audit logging (C13 = True)
    Verify C15 never got armed

```
- Now we create another script and paste code in guide
- This gives us the flag
