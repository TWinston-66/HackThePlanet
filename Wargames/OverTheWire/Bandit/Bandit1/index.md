---
layout: default
title: Bandit1
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/07/20
# Bandit: Level 0&rarr;1 

![bandit level-0-1](https://i.imgur.com/5Ry9aTa.png)

The goal of this level is to get the password for the next level out of the `readme` file 

To acommplish this we need to output the contents of a file

First we need to log in using the steps from the last level 

- Type the command `ssh bandit0@bandit.labs.overthewire.org -p 2220`
- Enter the password `bandit0`

To find this file we need to search the home directory for any directorys or files

- Type the command 	`ls` 

This displays all the files and directorys in the current (home) directory 

We can then see that a file named `readme` is outputed 

This is the file we are looking for 

- Type the command `cat readme` 

This outputs the contents of the file `readme`

Then the password for the next level gets outputed 

- Copy the password `boJ9jbbUNNfktd78OOpsqOltutMc3MY1`
- Type `exit` to logout 



[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit2/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit0){: .btn .btn-blue }


