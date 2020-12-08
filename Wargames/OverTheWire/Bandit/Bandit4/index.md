---
layout: default
title: Bandit4
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 3&rarr;4

![bandit level-3-4](https://i.imgur.com/YJadVrO.png)

The goal of this level it to get the password for the next level out of a hidden file that is located in the directory named `inhere` 

To accomplish this we need to navigate to the `inehere` directory then find and read the hidden file 

First we need to log into the level 

- Type the command `ssh bandit3@bandit.labs.overthewire.org -p 2220`
- Enter the password `UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK`

We know that the target file is inside the directory `inhere` that is located in the home directory, but we can check using the `ls` command

We then need to enter the directory using the command `cd`

- Type the command `cd inhere`

Once we need to then search for the file that contains the password and we can again use the `ls` command 

However this does not find anything because as we know the file is hidden 

To find a hidden file we can use `ls` but we need to add an argument to tell it to show us all of the file including hidden ones

- Type the command `ls -a` 

We can now see that there is a file called `.hidden` 

The `.` in front of `hidden` is what makes that file hidden 

Now we need to read the password from that file and we can use the `cat` command for that 

- Type the command `cat .hidden` 

Then the password for the next level gets outputted 

- Copy the password `pIwrPrtPN36QITSp3EQaw936yaFoFgAB`
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit3){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/docs/writeup-not-posted-bandit){: .btn .btn-blue }