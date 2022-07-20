---
title: "BONUS: transfer with SMB to the Classic RDS"
teaching: 20
exercises: 0
questions:
- "How can you access classic RDS from your local machine?"
- "How can you access classic RDS from Artemis?"
objectives:
- "Learn to move data from Artemis to Classic RDS"
- "Learn to move data from local to Classic RDS"
keypoints:
- "Use smbclient to move to windows-based protocols."
---

The older classic RDS used a windows based ```cifs``` filesystem, so required the ```samba``` protocol to connect to it. But these instructions may come in handy for **any** ```SMB``` filesystem you want to connect to.


## Transfer from Artemis to ‘classic RDS’ 

Your collaborator wants you to bring a local copy of the data to the conference next week. You don’t have much space for this massive dataset on your laptop, so you back it up to ‘classic RDS’ so you can easily show the data via your mapped network drive. 

***This part will be demonstrated.*** You do not have to perform this, as not all accounts are part of DASHR projects with Classic RDS access.

To map ‘classic RDS’ network drive, follow the instructions here. Note that the path will differ depending on when your RDS was created.

To transfer data between Artemis and classic RDS, we use an ftp-like command line tool called ‘smbclient’. FileZilla could be used, however this is not recommended (especially for large files) as the transfer is bottlenecked by your local computer. Smbclient performs a direct transfer. 

In general, to connect with smbclient use the command: 

```
smbclient <path> -U <unikey> -W SHARED 
```

In this case: 

~~~
smbclient //shared.sydney.edu.au/research-data -U ict_hpctrain1 -W SHARED 
~~~
{: .bash}


Note: the different command prompt ```\>``` instead of ```$```. Some Linux commands work (e.g. ```ls```, ```pwd```, ```cd```, ```mkdir```). Using the ```!``` in front of any normal linux expression will exectue the command on the "local/host" machine, otherwise the commands are executed on the "remote" machine.

By default, ‘prompting’ (the system prompts you between transferring each file and awaits ‘Y’ or ‘N’ input) is ON. By default, ‘recurse’ (recursively copy directories) is OFF. 

Since we want to copy our Output directory to classic RDS, we should turn prompt OFF and recurse ON: 

~~~
prompt off 
recurse on 
~~~
{: .bash}


Now, move into one of our project folders and make a directory for the dataset: 

~~~
cd PRJ-SIHnextgen

mkdir Dog_disease 

cd Dog_disease 
~~~
{: .bash}

Then transfer the Output directory and its contents: 

~~~
mput Output 
~~~
{: .bash}


<figure>
  <img src="{{ page.root }}/fig/pic11_smb.png" style="margin:10px;width:600px"/>
</figure><br>


The output data can now be readily accessed via the local file explorer under the mapped drive, without having to save the data onto your local hard drive 😊 

Single files can be transferred from Artemis to classic RDS with ```put```. Single files can be transferred from classic RDS to Artemis with ```get```, or multiple files with ```mget```. To log out of smblicent, enter ```control + C``` or type ```exit```.



Then mount away, put in your password when prompted:
```
sshfs <unikey>@research-data-int.sydney.edu.au:/rds/PRJ-<yourproject> /home/ubuntu/myRDS
```


<br>
