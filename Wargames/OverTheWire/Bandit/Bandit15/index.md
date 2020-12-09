---
layout: default
title: Bandit15
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 14&rarr;15

![bandit level-14-15](https://i.imgur.com/H3JCffd.png)

The goal of this level is to retrieve the password for the next level via port 30000 

To accomplish this we are going to be using piping and Netcat

First we need to log onto the level 

- Type the command `ssh bandit14@bandit.labs.overthewire.org -p 2220`
- Enter the password `4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e`

The command is submitting the password to port 30000 on local host 

- Type the command `echo "4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e" | nc localhost 30000` 

This command then outputs the password for the next level 

- Copy the password `BfMYroe26WYalil77FoDi9qh59eK5xNr` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit14){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit16){: .btn .btn-blue }