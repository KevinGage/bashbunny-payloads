# DumpCreds 2.1
* Original Author: QDBA
* Edited by: Kevin Gage
* Tested: Windows 10 english, Windows 8.1 english

## Description

** I took all of QDBA's great work and debugged it to work on my english language windows 10 machine.  Also tested on windows 8.1

** !!!!! works only at Bash Bunny with FW 1.1 !!!!! **

Dumps the usernames & plaintext passwords from 
 * Browsers (Crome, IE, FireFox)
 * Wifi 
 * SAM Hashes (only if AdminMode=True)
 * Mimimk@tz Dump (only if AdminMode=True)
 * Computerinformation (Hardware Info, Windows ProductKey, Hotfixes, Software, Local, AD Userlist)
 
 without 
 * Use of USB Storage (Because USB Storage ist mostly blocked by USBGuard or DriveLock)
 * Internet connection (becaus Firewall ContentFilter Blocks the download sites)
 
 
# Problems
- if you first use the payload on a computer, it will take some time and tries until the drivers are successfully loaded.
- If the payload doesnt work. (Red LED or Yellow LED blinks 2 or 4 times) plug off the BB  and try it once more (can take 3 or 4 times)
- If the payload stops working yellow LED blinks very fast longer than 2min. You get no white LED. Your run in a time out. 
  If you plugin the BB every payload has 1min 30sfor doing the job. At 1min 30s every payload stops. (Thats a FW 1.1 issue)  
 
# Debug 
For simplicitys sake I removed QDBA's debug functions.
 

## Configuration

None needed. 

## Requirements
https://github.com/CoreSecurity/impacket

## Download


https://github.com/KevinGage/bashbunny-payloads/tree/master/payloads/library/credentials/DumpCreds


## Install

1. Put Bash Bunny in arming mode

2. Copy the required files to the bash bunny(switchx is switch1 or switch2)
	* payloads/switchx/payload.txt --> the payload file
	* payloads/switchx/main.ps --> the main powershell script
	* payloads/switchx/PS --> the data collection powershell scripts
	* tools/impacket --> impacket tools (provide the smbserver.py) (not neccessary if you had already installed)
				
3. eject Bash Bunny safely!!

4. Insert Bash Bunny in arming mode ( Impacket and languages will be installed ) 		

5. move switch in right position

6. plugin Bash Bunny and have fun....! :-)


## STATUS

| LED                     | Status                                       |
| ----------------------- | -------------------------------------------- |
| Magenta Solid           | Setup                                        |
| Red slow blink          | Impacket not found                           |
| Red fast blink          | Target did not acquire IP address            |
| Yellow single blink     | Initialization                               |
| Yellow double blink     | HID Stage                                    |
| Yellow triple blink     | Wait for IP coming up                        |
| Yellow quad blink       | Wait for Handshake (SMBServer Coming up)     |
| Yellow very fast blink  | Powershell scripts running                   |
| White fast blink        | Cleanup, copy Files to <root>/loot           |
| Green              	  | Finished                                     |
| ----------------------- | -------------------------------------------- |


## Discussion

https://forums.hak5.org/index.php?/topic/40582-payload-drumpcreds-20-wo-internet-wo-usb-storage

## Credits

to...... 
https://github.com/qdba/bashbunny-payloads/tree/master/payloads/library/DumpCreds_2.0	QDBA << he wrote 99% of this thing!

https://github.com/EmpireProject/Empire         Get-FoxDump.ps1, Invoke-M1m1k@tz.ps1, Invoke-PowerDump.ps1, Get-ChromeCreds.ps1
