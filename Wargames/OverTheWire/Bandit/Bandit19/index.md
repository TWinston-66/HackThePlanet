---
layout: default
title: Bandit19
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 18&rarr;19

![bandit level-18-19](https://i.imgur.com/dI2UY3g.png)

The goal of this level is to get the password from a file named `readme` in the home directory 

To accomplish this we are going to use an ssh argument 

First we need to log onto the level 

- Type the command `ssh bandit18@bandit.labs.overthewire.org -p 2220`
- Enter the password `kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd`

However when we run this we get a message saying `Bye Bye!` then our connection gets disconnected 

This is caused by the modified `.bashrc` file 

The `.bashrc` file is run automatically and is responsible for creating a shell session

Because we don't have a shell to run a `cat` command on the `readme` file then we have to find a way to run a command without a shell

We can do that exact thing with an ssh argument 

- Type the command `ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat ~/readme"`

- Enter the password `kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd`

This command is running the `cat` command as soon as a connection is made 

This bypass the creation of a shell instance 

This can also be useful if we have a machine we are connecting to that we only have to run one command on 

When this is run the password is outputted 

- Copy the password `IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit18){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit20){: .btn .btn-blue }