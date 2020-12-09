---
layout: default
title: Bandit20
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 19&rarr;20

![bandit level-19-20](https://i.imgur.com/XjhgxYl.png)

The goal of this level is to the password for the next level from the `/etc/bandit_pass/bandit20` file 

To accomplish this we are going to take advantage of some escalated privileges on the setuid binary in the home directory 

First we need to log onto the level 

- Type the command `ssh bandit19@bandit.labs.overthewire.org -p 2220`
- Enter the password `IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x`

When we do a quick `ls` search we can see a file named `bandit20-do`

If we run a `file` command on that file we get back that the file is a `setuid ELF`

A setuid elf is a binary executable that has special permissions that allow for unprivileged users to run that program with elevated privileges if exploited right 

We can double check for the setuid flag by running `ls -l`  

The `-l` argument is searching for all files and providing more details on them 

In this case the detail we want are the permission flags so we can check for that setuid flag 

We can see that the permission flags for our setuid binary are `-rwsr-x---` 

The most important part of that is the `s` flag because that is the flag denoting setuid 

Now that we know the executable has special privileges we need to find out what it does and see if we can use it to get the password 

We can run the executable... 

- Type the command `./bandit20-do`

And we get the output...

`Run a command as another user.
  Example: ./bandit20-do id` 
  
If we run `./bandit20-do id` we get a list of the users it can be run as 

One if those users is bandit20...which means that when we run this file we run a command as bandit20 

Which also means we can use this file to gain the necessary rights to read the password for the next level 

- Type the command `./bandit20-do cat /etc/bandit_pass/bandit20` 

First we are running the file to get those access rights 

Then we are reading the contents of the bandit20 password file 

When this is run the `cat` command does its job and outputs the password 

- Copy the password `GbKksEFF4yrVs6il55v6gwY5aVje5f0j` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit19){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/docs/writeup-not-posted-bandit){: .btn .btn-blue }