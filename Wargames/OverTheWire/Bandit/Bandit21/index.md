---
layout: default
title: Bandit21
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/10/20
# Bandit: Level 20&rarr;21

![bandit level-20-21](https://i.imgur.com/d9PpAAf.png)

The goal of this level is to e the setuid binary to transit the password for the next level 

To accomplish this we are going to use the skills and knowledge around setuid binaries from last level in conjunction with a netcat listener 

First we need to log onto the level 

- Type the command `ssh bandit20@bandit.labs.overthewire.org -p 2220`
- Enter the password `GbKksEFF4yrVs6il55v6gwY5aVje5f0j`

When we do a quick `ls` search we can see a file named `suconnect`

If we run a `file` command on that file we get back that the file is a `setuid ELF`

We can double check for the setuid flag by running `ls -l`

We can see that the permission flags for our setuid binary are `-rwsr-x---` 

We can run the executable... 

- Type the command `./suconnect`

And we get the output...

`Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.` 

This means that we need to create a listener on our local machine so that when we run `./suconnect` we can get the password transmitted to us 

We can use the tool Netcat to create a listener 

 `nc -l localhost -p 61337` 
 
However we also need to submit the password from the previous level to `./suconnect`

To do this we are going to use the Netcat listener along with piping 

- Type the command `echo "GbKksEFF4yrVs6il55v6gwY5aVje5f0j" | nc -l localhost -p 61337` 

We then have to go back to the Bandit machine and run the `./suconnect` file with the port `61337` as an argument 

- Type the command `./suconnect 61337`

When this is run the password gets outputted 

- Copy the password `gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit20){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit22){: .btn .btn-blue }