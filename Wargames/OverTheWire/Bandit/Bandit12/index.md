---
layout: default
title: Bandit12
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 11&rarr;12

![bandit level-11-12](https://i.imgur.com/0qT9PJI.png)

The goal of this level is to get the password for the next level in a file called `data.txt` that has been encoded using Rot13 

To accomplish this we are going to use the `tr` command to decode the data inside the file and retrieve the password

Rot13 is a simple letter substitution cipher (Caesar Cipher) that replaces a letter with the 13th letter after it in the alphabet. 

First we need to log onto the level 

- Type the command `ssh bandit11@bandit.labs.overthewire.org -p 2220`
- Enter the password `IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR`

When we do a quick search with the `ls` command we can see that the file named `data.txt` is located in the home directory

If we output the data using the `cat` command we get an output of a string that looks very similar to the password format however we can tell that is encoded with Rot13

To decode the Rot13 we need to use the `tr` command

- Type the command `cat data.txt | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'`

The Caesar Cipher shifts plaintext three letters to the left to create ciphertext.

In this case, tr '[A-Z]' '[X-ZA-W]', tr translates all occurrences of 'A' to 'X', 'B' to 'Y', 'C' to 'Z', 'D' to 'A', etc.

[X-ZA-W] just means that your output starts with the letter X and continues through the letter Z, then continues with the letter A through the letter W. You could also use [XYZABCDEFGHIJKLMNOPQRSTUVW] instead but tr understands the hyphen '-' to mean 'through'.

When this command is run it outputs `The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu`

- Copy the password `5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit11){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit13){: .btn .btn-blue }