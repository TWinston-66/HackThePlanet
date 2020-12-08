---
layout: default
title: Bandit6
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 5&rarr;6

![bandit level-5-6](https://i.imgur.com/mcktwpp.png) 

The goal of this level is very similar to the last level. We have to find a human-readable file however this time we have more info to use to find the file among an even bigger group to search through

To accomplish this we are going to navigate into the `inhere` directory then search for the file that meets all of the requirements using the find command 

First we need to log onto the level 

- Type the command `ssh bandit5@bandit.labs.overthewire.org -p 2220`
- Enter the password `koReBOKuIDDepwhWk7jZC0RTdopnAYKh`

We then need to navigate into the `inhere` directory again using the `cd` command 

Once inside we can see a whole bunch of directories that contain even more files 

For this search we can use the `find` command with some arguments 

- Type the command `find ./ -type f -size 1033c ! -executable`

In the command we use the `find` command which allows us to search for specific files

The `./` part looks for all files including hidden ones

The `-type f -size 1033c` part looks for file that are 1033 bytes in size 

Finally the `! -executable` looks for files that are not executables 

The command will output any files that meet all of those requirements

When we run the command it gives us the file `./maybehere07/.file2`

This output tells us that the file is a file inside the directory `maybehere07` named `file2` 

To read the data from that file we can use the `cat` command 

- Type the command `cat ./maybehere07/.file2`

Then the password for the next level gets outputted 

- Copy the password `DXjZPULLxYr17uwoI01bNLQbtFemEgo7` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit5){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit7){: .btn .btn-blue }