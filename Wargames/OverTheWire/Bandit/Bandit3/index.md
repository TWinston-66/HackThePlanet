---
layout: default
title: Bandit3
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 2&rarr;3 

![bandit level-2-3](https://i.imgur.com/O1k8zy9.png)

The goal of this level is to get the password for the next level out of the file name `spaces in this filename`

To accomplish this we need to know how to handle spaces in file names

First we need to log into the level 

- Type the command `ssh bandit2@bandit.labs.overthewire.org -p 2220`
- Enter the password `CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9`

We know that the target file is located in the home directory but we can check using the `ls` command  

To read the file we need to add `'` before and after the file name 

- Type the command `cat 'spaces in this filename'`

We add the `'` so that the machine can recognize the spaces that are being used in the file name 

Then the password for the next level gets outputed 

- Copy the password `UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK`
- Type `exit` to logut

[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit2){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/docs/writeup-not-posted.md){: .btn .btn-blue }
