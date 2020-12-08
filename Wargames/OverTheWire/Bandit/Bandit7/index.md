---
layout: default
title: Bandit7
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 6&rarr;7

![bandit level-6-7](https://i.imgur.com/h6tbqej.png) 

The goal is this level is to to locate a file that is somewhere on the server that has a certain size and is owned by certain a certain user and group

To accomplish this we are going to once again use the find command 

First we need to log onto the level 

- Type the command `ssh bandit6@bandit.labs.overthewire.org -p 2220`
- Enter the password `DXjZPULLxYr17uwoI01bNLQbtFemEgo7`

If we do a quick search for any files in the home directory using the `ls` command we can see that nothing gets outputted

This means the file is most likely hidden 

So we are going to execute the search from the home directory 

- Type the command `find / -user bandit7 -group bandit6 -size 33c` 

We are using the find command to find our password file with those specifications

The `/` part of the command is to look for all files 

The `-user bandit7 -group bandit6` part is looking for a file that is owned by both that user and that group 

The `-size 33c` part is looking for a file that is 33 bytes in size

When this command is run we get a list of files that it found matching those requirements 

However we can see that we do not have permission to view all of the files except one

That one file we can work with is our password file that is called...

`/var/lib/dpkg/info/bandit7.password`

We can read the data from that file using the `cat` command 

- Type the command `cat /var/lib/dpkg/info/bandit7.password`

Then the password for the next level gets outputted 

- Copy the password `HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit6){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit8){: .btn .btn-blue }