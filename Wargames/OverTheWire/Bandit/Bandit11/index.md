---
layout: default
title: Bandit11
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 10&rarr;11

![bandit level-10-11](https://i.imgur.com/JGMGAkB.png)

The goal of this level is to get the password for the next level in a file called `data.txt` that is encoded with base64 

To accomplish this we are going to use the `base64` command to decode the data inside the file and retrive the password 

First we need to log onto the level 

- Type the command `ssh bandit10@bandit.labs.overthewire.org -p 2220`
- Enter the password `truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk`

When we do a quick search with the `ls` command we can see that the file named `data.txt` is located in the home directory

If we output the data using the `cat` command we get an output of a string that looks very similar to the password format however we can tell that is encoded with base64 

To decode the string from base64 we need to use the `base64` command

- Type the command `cat data.txt | base64 -d` 

When this command is run it will decode the output of the `cat` command from base64 

It then outputs `The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR`

- Copy the password `IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit10){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit12){: .btn .btn-blue }