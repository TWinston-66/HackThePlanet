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