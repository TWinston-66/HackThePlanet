---
layout: default
title: Bandit9
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 8&rarr;9

![bandit level-8-9](https://i.imgur.com/NCJ6yoK.png)

The goal of this level is to get the password for the next level in a file called `data.txt` in the string that only occurs once 

To accomplish this we can use piping and the sort command to find the only unique string in the file 

First we need to log onto the level 

- Type the command `ssh bandit8@bandit.labs.overthewire.org -p 2220`
- Enter the password `cvX2JJa4CFALtqS87jk27qwqGhBM9plV`

When we do a quick search with the `ls` command we can see that the file named `data.txt` is located in the home directory

If we output the data using the `cat` command we get an output of a lot of strings 

We need to search for the only unique string 

- Type the command `cat data.txt | sort | uniq -c`

This gives us a list of all the strings in the file and the amount of times they appear 

However there is one string that only appears one time and that is our password for the next level 

- Copy the password `UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit8){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit10){: .btn .btn-blue }