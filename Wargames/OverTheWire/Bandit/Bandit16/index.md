---
layout: default
title: Bandit16
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 15&rarr;16

![bandit level-15-16](https://i.imgur.com/8mjMAtN.png)


The goal of this level is to retrieve the password for the next level via port 30001 and SSL encryption

To accomplish this we are going to be using piping and openssl

First we need to log onto the level 

- Type the command `ssh bandit15@bandit.labs.overthewire.org -p 2220`
- Enter the password `BfMYroe26WYalil77FoDi9qh59eK5xNr`

We need to encrypt the password and submit it to port 30001 

To do this we are going to use the `openssl` command 

- Type the command `echo "BfMYroe26WYalil77FoDi9qh59eK5xNr" | openssl s_client -connect localhost:30001 -ign_eof`

This command is piping the password to openssl 

The `openssl s_client` part is instantiating a client in which we can use the connect to port 30001 

We then use the `-connect` argument to connect to that port on localhost 

Then we use the `-ing_eof` to stop the port from stopping our connection 

When we run the command we get the next password 

- Copy the password `cluFn7wTiGryunymYOu4RcffSxQluehd`
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit15){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit17){: .btn .btn-blue }