---
layout: default
title: Bandit8
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 7&rarr;8

![bandit level-7-8](https://i.imgur.com/R9ScQkU.png) 

The goal of this level is to get the password for the next level in a file called `data.txt` next to the word millionth 

To accomplish this we are going to use the `grep` command 

First we need to log onto the level 

- Type the command `ssh bandit7@bandit.labs.overthewire.org -p 2220`
- Enter the password `HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs`

When we do a quick search with the `ls` command we can see that the file named `data.txt` is located in the home directory 

If we output the data using the `cat` command we get an output of a lot of strings 

We need to search those strings for the word millionth and we can do that using `grep` 

- Type the command `cat data.txt | grep "millionth"` 

This command searches the output of the `cat` command for the string that includes the word `millionth` 

Once the command is run we get the string that contains the password 

- Copy the password `cvX2JJa4CFALtqS87jk27qwqGhBM9plV` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit7){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/docs/writeup-not-posted-bandit){: .btn .btn-blue }