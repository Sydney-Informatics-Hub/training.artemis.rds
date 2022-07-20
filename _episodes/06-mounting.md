---
title: "Mounting RDS on your system"
teaching: 5
exercises: 5
questions:
- "How can you access RDS from your local machine?"
objectives:
- "Learn to move data from RDS to your local machine"
keypoints:
- "Map a local network mount"
---

## Mounting RDS on your local machine.
Dependng on your operating system there are few ways to mount the RDS as a network drive. Keep in mind you must **BE ON THE UNIVERSITY NETWORK/VPN**.

These steps for Windows 10 are:

* Click on This PC from the Desktop.
* On the Computer tab, click on Map network drive in the Network section.
* Choose a drive letter and enter your Classic RDS path: ```\\shared.sydney.edu.au\research-data```.
* Enter ```SHARED\<UniKey>``` and your password.
* Click Finish.

<figure>
  <img src="{{ page.root }}/fig/pic09_classicmount.png" style="margin:10px;width:600px"/>
</figure><br>

Done! Now drag and drop and use as a normal network attache drive. 


## On Mac and Linux
To mount on Linux or Mac operating systems, you can use the smb network communication protocol (also known as CIFS) by mounting the path. 
On Mac OSX this feature is located from ```Finder > Go > Connect to Server```. In the ```Server Address``` use:

```
smb://shared.sydney.edu.au/research-data
```
Then use Name:```<UniKey>``` and Password:```<unikey password>``` as a Registered User. 
 
For a full discussion, and further mounting instructions for Windows/Mac OSX, and Linux, see here:
[https://sydneyuni.atlassian.net/wiki/spaces/RC/pages/228589620/Research+Data+Store](https://sydneyuni.atlassian.net/wiki/spaces/RC/pages/228589620/Research+Data+Store)


## On Linux Command Line/Terminal with the RDS
If you prefer to use the command line, the easiest way to mount the RDS is using a tool called ```sshfs``` which connects via the ```ssh``` protocol and performs file transfers using ```sftp```. 

Firstly install ```sshfs```. There are many ways to do this depending on your specific flavour of Unix/OSX, on Ubuntu for instance one can run:
```
sudo apt install sshfs
```

Create a directory where you want the mounted data to reside:
```
mkdir /home/ubuntu/myRDS
```

Then mount away, put in your password when prompted:
```
sshfs <unikey>@research-data-int.sydney.edu.au:/rds/PRJ-<yourproject> /home/ubuntu/myRDS
```

Note, becuase of the use of the ```sftp``` protocol you can use this same approach to mount off-network ```research-data-ext.sydney.edu.au``` and even ```hpc.sydney.edu.au``` drives. 

<br>
