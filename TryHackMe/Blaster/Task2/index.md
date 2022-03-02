---
layout: default
title: Task2
nav_exclude: true
parent: Blaster
grandparent: TryHackMe
---

### Written By: TWinston-66 
### 2/15/22
# Blaster: Task 2

For this question, we have to figure out how many open ports there are on the target machine. 

To accomplish this, we need to use nmap to conduct a port scan on the machine.

If you are unfamiliar with nmap, I would suggest doing to [nmap](https://tryhackme.com/room/furthernmap) room. 

First we need to run the nmap scan to enumerate the machine's ports and services 

- Type the command `nmap -A 10.10.198.85 -Pn`

The `-A` flag enables an "aggressive" scan which enables OS detection and version detection along with a port scan. 

The `-Pn` flag tells nmap to treat all given hosts as online, skipping the host discovery phase of the scan. 

- This flag is needed because this means blocks all pings so nmap decides the host is offline and doesn't do any scans. 

We could get the amount of open ports by running the same scan but without the `-A` flag, but the aggressive scan give us information that we will need later on in the room.

Once the scan has run, we can see that there are `2` ports open on this machine. 
- `80`
- `3389`

From the results of the same scan, we can see that there is a web server running 

Nmap is able to show us the `http-title` 
- `IIS Windows Server`

When then have to fuzz the web server for any hidden directories 

Fuzzing is the process of using a list of possible directory names, to try and find any hidden directories on the web server 

For this task, we can use `gobuster`

I am using the Seclists-Master wordlist for hidden directory fuzzing 
- https://github.com/danielmiessler/SecLists

The command is...
- `gobuster -w directory-list-2.3-medium.txt -u [machine IP]`

After letting this run for a while, some directory begin to show up. After trying the directories are being found, the one that is important is...
- `/retro`

The directory brings us to a blog type webpage and the blogs are written by the username...
- `wade`

This is out potential username 

After continueing to go through the blog site, we come across a post that has a potential username... 
- `parzival` 


Once we have this username and password, we need to use them to RDP into the target machine 