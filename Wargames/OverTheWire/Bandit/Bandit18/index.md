---
layout: default
title: Bandit18
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 17&rarr;18

![bandit level-17-18](https://i.imgur.com/grQdpTx.png)

The goal of this level is to compare the two password files to identify and extract the password for the next level 

To accomplish this we are going to use the `diff` command 

First we need to log onto the level 

Logging onto this level is going to be different because we have to use the RSA key we obtained last level 

- Type the command `ssh bandit16@bandit.labs.overthewire.org -p 2220 -i bandit17.key`

We are using the `-i` to specify the use of an ssh key 

Now that we are logged in we can do a quick `ls` search to check that both the files are in the home directory 

We now have to compare the two files 

To do this we are going to be using the `diff` command 

- Type the command `diff passwords.new passwords.old` 

The first result is our password 

The second is red herring that can be tested using some additional arguments 

- Copy the password `kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd`
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit17){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit19){: .btn .btn-blue }