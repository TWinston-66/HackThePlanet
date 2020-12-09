---
layout: default
title: Bandit13
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/08/20
# Bandit: Level 12&rarr;13

![bandit level-12-13](https://i.imgur.com/RmLrRom.png)

The goal of this level is to decompress the original file until we get a text file that we can read the password from

To accomplish this are going to make a reverse hex dump then use many different compression commands to decompress the file 

First we need to log onto the level 

- Type the command `ssh bandit12@bandit.labs.overthewire.org -p 2220`
- Enter the password `5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu`

When we do a quick search with the `ls` command we can see that the file named `data.txt` is located in the home directory

Before we continue we are going to do what the challenge problem suggests 

We are going to create a directory to work in, inside the `/tmp` where temporary files and directories are stored in linux

- Type the command `mkdir /tmp/bandit12`

We then copy the original `data.txt` into that directory 

- Type the command `cp data.txt /tmp/bandit12`

We then go into our tmp directory to begin working

- Type the command `cd /tmp/bandit12`

If we output the data using the `cat` command we get an output of a hex dump of a file named `data2.bin` 

- `cat data.txt`

We can then do a reverse hex dump with the command `xxd` command then store it in a file named `data` 

- Type the command `cat data.txt | xxd -r > data`

We then need to determine the type of file our new file named `data` is 

We can do this with the `file` command 

- Type the command `file data` 

This command then tells us that it is a gzip compressed file 

Because of the challenge prompt we can assume that the next step is to unzip that file  

But first we have to make sure our tools can recognize the file as a gzip 

To do this we are going to use the `mv` command 

- Type the command `mv data data2.gz`

We are renaming the original `data` file to a `.gz` file 

We add the number each time we rename to we can keep track of the files we have made and changed 

Now we need to unzip our new file and to do that we are going to use the `gzip` command 

- Type the command `gzip -d data2.gz`

If we run and `ls` we can see that a new file named `data2` was extracted 

We then run a `file` command on that file 

- Type the command `file data2` 

We can then see that the new file is a `bzip2` file 

And once again we have to extract this file but first we have to rename it 

- Type the command `mv data2 data3.bz` 

To extract this file we use the `bzip2` command 

- Type the command `bzip2 -d data3.bz` 

Then we continue this process of extracting and renaming the files until we are left with a text file that contains the raw password

Instead of explaining each steps I have just put the rest of the commands in a code snippet below 

`mv data3 data4.gz` 

`gzip -d data4.gz`

`file data4`

`mv data4 data5.tar`

`tar -xf data5.tar`

`file data5.bin`

`mv data5.bin data6.tar`

`tar -xf data6.tar`

`file data6.bin`

`mv data6.bin data7.bz`

`bzip2 -d data7.bz`

`file data7`

`mv data7 data8.tar`

`tar -xf data8.tar`

`file data8.bin`

`mv data8.bin data9.gz`

`gzip -d data9.gz`

`file data9`

Finally we are left with a text file named `data9` 

We can use the `cat` command the view the password 

- Type the command `cat data9`

When this command is run it outputs `The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL`

- Copy the password `8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit12){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit14){: .btn .btn-blue }