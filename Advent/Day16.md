# Forensics - Registry Furensics
> Learn what the Windows Registry is and how to investigate it.

## Task 1: Introduction
- I was asked to turn on the target machine
- I did that and moved on to part 2

## Task 2: Investigate the Gifts Delivery Malfunctioning
- An analogy was made on how windows registry is similar to our brain and overview of registry was given
- Different hive named with examples were given and what important stuff they contained was also mentioned
- Actual paths in registry editor were provided for their respective hives
- Example of how we can see connected USB devices through registry editor was shown (by accessing path: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR`)
- Similarly another example showed we can access `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU` to see programs ran by user
- Then the main part of this topic was mentioned which talked about how we can perform forensics by extracting and analysing registry data
- A table is shared with common and useful paths to check for forensics purposes
- A common tool used to aid in such tasks is [registry explorer](https://ericzimmerman.github.io/)

### Answers:
- First loaded the hive's SYSTEM as instructed and got the basic idea
- Now I went to the main table and it mentioned I should go to `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall` for installed apps info
- So I loaded `SOFTWARE` (and two other LOG files) hive and went to the shown path
- The answer was `DroneManager Updater` on 21st october timestamp before abnormal activity
- Second answer was `C:\Users\dispatch.admin\Downloads\DroneManager_Setup.exe` 
- Third answer was `"C:\Program Files\DroneManager\dronehelper.exe" --background`
