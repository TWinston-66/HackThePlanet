---
layout: default
title: Bandit10
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 9&rarr;10

![bandit level-9-10](https://i.imgur.com/y5E6ql4.png)

The goal of this level is to get the password for the next level in a file called `data.txt` that has several `=`s in front of it

We can accomplish this by using the `strings` command to list all of the different strings in the file

First we need to log onto the level 

- Type the command `ssh bandit9@bandit.labs.overthewire.org -p 2220`
- Enter the password `UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR`

When we do a quick search with the `ls` command we can see that the file named `data.txt` is located in the home directory

If we output the data using the `cat` command we get an output of a lot of strings and characters 

To sort through those characters we need to separate the `strings` command

- Type the command `strings data.txt`

Then we can scroll down and we can see that there are many strings that are preceded by equal signs 

The last string that is preceded by equal signs are in the same format and length as past passwords so that is our password 

- Copy the password `truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit9){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit11){: .btn .btn-blue }