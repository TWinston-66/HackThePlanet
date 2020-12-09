---
layout: default
title: Bandit14
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 13&rarr;14

![bandit level-13-14](https://i.imgur.com/TPX9Hd1.png)

The goal of this level is to obtain the private ssh key that we can use to log into the next level 

Remember that `localhost` is the hostname of the machine you are working on 

To accomplish this we are going to use the `head` command as well as some ssh arguments 

First we need to log onto the level 

- Type the command `ssh bandit13@bandit.labs.overthewire.org -p 2220`
- Enter the password `8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL`

When we do a quick search with the `ls` command we can see that there is a file named `sshkey.private` is located in the home directory

If we run a `file` command to identify the file type we can then see that it is a `PEM RSA private key`

A `PEM RSA private key` is a private key format that stores an RSA private key, for use with cryptographic systems like ssh in this case 

An RSA key ia a key that is encoded using PEM encoding which is an algorithm that uses base64 to encode 

If we output the data using the `cat` command we get an output of an RSA key 

This is the key that we need to use to login to the next server to get the Level 14 password 

We can use this key and ssh in unison 

- Type the command `ssh bandit14@localhost -i sshkey.private`

The `-i` argument is setting the `sshkey.private` file as the identity or login info to use

Once we have been logged in then we can go to `/etc/bandit_pass` as instructed in the challenge problem 

- Type the command `cd /etc/bandit_pass`

With a quick `ls` search we find a bunch of text files containing the password to all of the levels however we only have permission to view the file for bandit14 

We can do a `cat` output and get the password 

- Copy the password `4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit13){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit15){: .btn .btn-blue }