---
layout: default
title: Task2
nav_exclude: true
parent: CrackTheHash
grandparent: TryHackMe
---

### Written By: TWinston-66 
### 7/15/21
# Crack The Hash: Task 2

## Hash #1

![Hash1](https://i.imgur.com/UMuqni7.png)
 
 Remember to add the new hash to the `hash.hash` file 
 
 First we need to find out what type of hash this hash is..
 
 We will again be using the TunnelsUP Hash Analyzer 
 
 Hash Analyzer tells us that this hash is a SHA2-256 hash
 
 This hash can be cracked using the command...
 
 - hashcat -m 1400 hash.hash rockyou.txt

When this command is run, you should get an output similar to this...

![Cracked1](https://i.imgur.com/6k7lUnz.png)

  You can read all of the stats that Hashcat gave us but the important part is the place where it gives us the cracked hash
  
  `F09EDCB1FCEFC6DFB23DC3505A882655FF77375ED8AA2D1C13F640FCCC2D0C85: *CRACKED HASH RESULT*`

  
  ## Hash #2
  
  ![Hash2](https://i.imgur.com/a1K26Wv.png)
  
  The hint tells us that this hash is a NTLM hash
  
  This hash can be cracked using the command...
  
  - hashcat -m 1000 hash.hash rockyou.txt

When this command is run, you should get an output similar to this...

![Cracked2](https://i.imgur.com/exV1wSy.png)

  You can read all of the stats that Hashcat gave us but the important part is the place where it gives us the cracked hash
  
  `1DFECA0C002AE40B8619ECF94819CC1B: *CRACKED HASH RESULT*`