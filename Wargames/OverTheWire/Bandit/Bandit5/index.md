---
layout: default
title: Bandit5
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 4&rarr;5

![bandit level-4-5](https://i.imgur.com/SEGWnb8.png) 

The goal of this level is to get the password out of the only human-readable inside the `inhere` directory 

The tip given is a good tip that was discussed in level 0 

To accomplish this we to navigate to the `inhere` directory and search for a file that is human-readable then read the contents from that file to get the password 

First we need to log into the level 

- Type the command `ssh bandit4@bandit.labs.overthewire.org -p 2220`
- Enter the password `pIwrPrtPN36QITSp3EQaw936yaFoFgAB`

We need to navigate into the `inhere` directory using the `ls` command 

Once there we can use the `file` command to search for data types to identify the only human-readable file 

The `file` command allows us to identify the file type (such as text or executable) and the type of data that is contained in the file 

- Type the command `file ./-file*`

This `file` command searches for all files which is denoted by `*`, including hidden ones which is denoted by `./`  

The `-file` part of the command is going to output the data type of the data inside of any files that have `-file` in their names

Once the command has ran we can see that it has outputted all the files and their data types

We can then see that the only file that does not have the data type of `data` is file `-file07`

It shows the data type as `ASCII text` which is text that we humans can recognize as letters of the English alphabet 

To read the data from that file we can again use the `cat` command 

However we have to handle the `-` in the file name 

To do that we need to put `./` in front of the file

- Type the command `cat ./-file07`

Then the password for the next level gets outputted 

- Copy the password `koReBOKuIDDepwhWk7jZC0RTdopnAYKh` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit4){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit6){: .btn .btn-blue }