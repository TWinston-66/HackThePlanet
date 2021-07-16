---
layout: default
title: Task1
nav_exclude: true
parent: CrackTheHash
grandparent: TryHackMe
---

### Written By: TWinston-66 
### 7/15/21
# Crack The Hash: Task 1

## Hash #1

![Hash1](https://i.imgur.com/s3EDF4A.png)

To crack these hashes I am going to be using Hashcat as I find it to be very efficient as it takes advantage of my GPU 
  
  I am also going to be using the RockYou.txt password list. The list can be downloaded from the link below. 
  
  [RockYou List](https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt){: .btn .btn-blue }
  
  This hash can be cracked using the command...
  
  - hashcat -m 0 hash.hash rockyou.txt
  
  The `-m 0` part of the command gives the hash type -- in this case md5 (All hash types can be found using the hashcat help menu `hashcat --help`)
  
  The `hash.hash` is the file that I put the hash into -- This just allows for a cleaner command
  
  Finally there is the file path to the RockYou password list 
  
  When this command is run, you should get an output similar to this... 
  
  ![Cracked1](https://i.imgur.com/vo95V5A.png)
  
  
  You can read all of the stats that Hashcat gave us but the important part is the place where it gives us the cracked hash
  
  `48bb6e862e54f2a795ffc4e541caed4d: *CRACKED HASH RESULT*`


  ## Hash #2
  
  ![Hash2](https://i.imgur.com/K6xTwiX.png)
  
  As described in the hint we need to figure out which version of SHA this hash is 
  
  To do this we can use a tool on TunnelsUP called Hash Analyzer 
  
  ![Analyze2](https://i.imgur.com/NC9l6eD.png)
  
  Hash Analyzer tells us that this hash is a SHA1 hash
  
  Remember to add the new hash to the `hash.hash` file 
  
  This hash can be cracked using the command... 
  
  - hashcat -m 100 hash.hash rockyou.txt
  
  We use `-m 100` to give us the SHA1 hash type 
  
  When this command is run, you should get an output similar to this... 
  
  ![Cracked2](https://i.imgur.com/LDWK1Uo.png)
  
  You can read all of the stats that Hashcat gave us but the important part is the place where it gives us the cracked hash
  
  `cbfdac6008f9cab4083784cbd1874f76618d2a97: *CRACKED HASH RESULT*`


## Hash #3 
  
  ![Hash3](https://i.imgur.com/QJjAglL.png)
  
 Once again we can use the TunnelsUP Hash Analyzer to tell us which version of SHA this hash is 
 
 ![Analyze3](https://i.imgur.com/QP0rtvK.png)
 
 Hash Analyzer tells us that this hash is a SHA2-256 hash
 
 Remember to add the new hash to the `hash.hash` file 

 This hash can be cracked using the command... 
 
 - hashcat -m 1400 hash.hash rockyou.txt

We use `-m 1400` to give us the SHA2-256 hash type

When this is command is run, you should get an output similar to this...

(Here I switched to Ubuntu 21.04) 

![Cracked3](https://i.imgur.com/3viXIxT.png)

You can read all of the stats that Hashcat gave us but the important part is the place where it gives us the cracked hash

`1C8BFE8F801D79745C4631D09FFF36C82AA37FC4CCE4FC946683D7B336B63032: *CRACKED HASH RESULT*`


## Hash #4
  
  ![Hash4](https://i.imgur.com/lxdIFYU.png)
  
  Checking the hash with TunnelsUP tells us that this hash is a `bcrypt` hash
  
  Remember to add the new hash to the `hash.hash` file 
  
  In the hint it tells us that this type of hash can take a long time to crack...
  
  As you can see, hashcat gives me the estimate of over 12 days to brute-force crack the hash
  
  ![Hash4_Estimate](https://i.imgur.com/hf62DRI.png)
  
 The hint tells us to filter the rockyou list for four letter words, so that is what I decided to do
 
 I ended up writing a quick python script that creates a new list named `rockyou_filtered.txt` that contains only the four letter passwords from the original rockyou list
 
 Here is the code...

```python
######### Filter RockYou Password List for x amount letter words #########

# Read in RockYou List
file1 = open('rockyou.txt', 'r')
Lines = file1.readlines()
file1.close()

# Set target word length
word_length = 4

# Filter Line by Line + Write all target length words to list
length = len(Lines)

file2 = open('rockyou_filtered_2.txt', 'w')

for line in Lines:
    line = line.replace("\n", '')
    if len(line) == word_length:
        file2.writelines(line + '\n')

file2.close()
```

To use this script just put a file called `filter.py` in the same directory as your rockyou.txt file then run it using...

- python3 filter.py 

Just as a word of warning, this is definitely not the fastest way to accomplish this, this is just the way I did it

Also beware the script does take a little bit to run 

Finally, now that we have an updated wordlist we can crack the hash using the command...
- hashcat -m 3200 hash.hash rockyou_filtered.txt -w 3

Here we use the `-m 3200` to crack bcrypt hashes 

I use the `-w 3`  option to set the workload to performance level 3...

This simply puts a higher workload on the system to make the crack run faster 

Warning! hashcat does say that level 3 will make the desktop unresponsive while running...

```
- [ Workload Profiles ] -

  # | Performance | Runtime | Power Consumption | Desktop Impact
 ===+=============+=========+===================+=================
  1 | Low         |   2 ms  | Low               | Minimal
  2 | Default     |  12 ms  | Economic          | Noticeable
  3 | High        |  96 ms  | High              | Unresponsive
  4 | Nightmare   | 480 ms  | Insane            | Headless

```
When this command is run, you should get an output similar to this...

![Cracked4](https://i.imgur.com/oKWEQnx.png)

You can read all of the stats that Hashcat gave us but the important part is the place where it gives us the cracked hash

`$2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom: *CRACKED HASH RESULT*`


## Hash #5
  
  ![Hash5](https://i.imgur.com/520yrOM.png)
  
  The hint tells us that the hash is an MD4 hash
  
  Remember to add the new hash to the `hash.hash` file 
  
  When you try and crack the hash using the rockyou list like we have been, using the command... 
  
  - hashcat -m 900 hash.hash rockyou.txt

We get the status output from hashcat saying `Exhausted`

This means that hashcat has run through every possible password in the list and failed to crack the hash against every singe one 

This is because this password is not in the rockyou password list

I ended up using the CrackStation password list which can be downloaded here...

 [CrackStation List](https://crackstation.net/crackstation-wordlist-password-cracking-dictionary.htm){: .btn .btn-blue }
 
 I recommend downloading the http mirror version as it is easier to deal with after downloading it, even though it is slower
 
 After you have download we need to decompress (`-d`) the `.gz` archive file, which can be done using the command...
 
 - gzip -d crackstation.txt.gz

This command will take a little bit to run 

We can then crack the hash with the new wordlist, using the command... 

- hashcat -m 900 hash.hash crackstation.txt -w 3 

The command will first take a little bit to build a dictionary cache before it starts trying to crack the hash

When this command is run, you should get an output similar to this...

![Cracked5](https://i.imgur.com/6uudtde.png)

You can read all of the stats that Hashcat gave us but the important part is the place where it gives us the cracked hash

`279412f945939ba78ce0758d3fd83daa: *CRACKED HASH RESULT*`