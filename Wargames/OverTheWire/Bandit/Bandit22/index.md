---
layout: default
title: Bandit22
nav_exclude: true
parent: Bandit
grandparent: OverTheWire
---

### Written By: TWinston-66 
### 12/10/20
# Bandit: Level 21&rarr;22

![bandit level-21-22](https://i.imgur.com/vWPSh9e.png)

The goal find what command is being run by the Cron configuration to get the password for the next level 

To accomplish this we are going to need to understand what Cron is and how it works 

First we need to log onto the level 

- Type the command `ssh bandit21@bandit.labs.overthewire.org -p 2220`
- Enter the password `gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr`

Once we are logged in we look in the `etc/cron.d/` as the challenge suggests 

- Type the command `cd /etc/cron.d/`

If we do a quick search with `ls` we can find a bunch of files with the same naming scheme `cronjob_bandit...`

First we need to understand what Cron is and what these files are

Cron is a time based task schedular in Unix systems 

A Cron Job is the task itself 

A Crontab is a file that regulates and schedules the different Cron Jobs 

The files inside `etc/cron.d/` are a bunch of Crontab files 

If we output the contents of the Crontab named `cronjob_bandit22` then we get the instructions for how Cron is going to handle that job 

`@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null`
`* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null`

We can see that it is going to run a file -- `/usr/bin/cronjob_bandit22.sh`

If we go to that directory we can see that there is a bunch of shell scripts (`.sh`) that are run by the Cron Jobs in the `/etc/cron.d/` directory 

If we output the contents of `cronjob_bandit22.sh` using `cat` we can see what that shell script does when run 

`chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv` means modifying the permission of that file 

`cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`
redirects the bandit22‘s password to the t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv file, located in tmp.

Knowing that the password for the next level is stored inside `/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv` we can just dump the contents using `cat`


- Copy the password `Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI` 
- Type `exit` to logout





[Bandit](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/){: .btn .btn-blue }
[Back](https://twinston-66.github.io/HackThePlanet/Wargames/OverTheWire/Bandit/Bandit21){: .btn .btn-blue }
[Next Level](https://twinston-66.github.io/HackThePlanet/docs/writeup-not-posted-bandit){: .btn .btn-blue }