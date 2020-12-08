---
layout: default
title: Bandit2
nav_exclude: true
---

### Written By: TWinston-66 
### 12/07/20
# Bandit: Level 1&rarr;2

![bandit level-1-2](https://i.imgur.com/Dz8iX06.png)

The goal of this level is to get the password for the next level out of the file named `-`

To accomplish this we need to know how to handle special characters in file names 

First we need to log into the level 

- Type the command `ssh bandit1@bandit.labs.overthewire.org -p 2220`
- Enter the password `boJ9jbbUNNfktd78OOpsqOltutMc3MY`

We know that the target file is located in the home directory but we can check using the `ls` command 

To read the file we need to add a `./` before the file name 

- Type the command `cat ./-` 

We add the `./` so that the machine can recognize the special character `-` that is being used as the file name 

Then the password for the next level gets outputed

- Copy the password `CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9`
- Type `exit` to logout


[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit1){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit3/){: .btn .btn-blue }

