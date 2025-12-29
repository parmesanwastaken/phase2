# Race Conditions - Toy to The World
> Learn how to exploit a race condition attack to oversell the limited-edition SleighToy.

## Task 1: Introduction
- I am asked to turn on attaxk box and target machine
- I turned them and moved to part 2

## Task 2: Race Condition
- Race condition is talked about, which happens when two or more conditions occur together
- Three types are talked bout with a brief description
- For this task the setup requires to send all all browser requests to burp suite through foxyproxy addon and running burp suite on desktop
- We create a `Temporary project in memory` and select the default config
- Then we start it and use proxy and repeater option to exploit race conditions (while ensuring that interscept is off)
- Now we go to the site and login with credentials given in guide
- We order and pay for `SleighToy Limited Edition`

### Answers:
- Now that we have done basic steps, we exploit it
- We find the POST request to `/process_checkout` in burp suite
- Now we switch to repeater tab and add it using instructions in guide
- Then we duplicate this tab group multiple times
- Finally we send it
- The exploit is done and as we can see on original website, the stock is in negative
- Also the flag is shown
- We repeat the same for `Bunny Plush (Blue)` to get second flag 
