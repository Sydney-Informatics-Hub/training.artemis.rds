---
title: "Transfer from LOCAL to Artemis HPC"
teaching: 20
excercises: 10
questions:
- "What tools can you use to copy data to a remote machine?"
objectives:
- "Learn to move data between local machine and remote HPC environemnt"
keypoints:
- "Use scp"
- "Use GUI like Filezilla"
---

# Transfer from LOCAL to Artemis HPC

Back to the case study... Since you have not run this kind of analysis before, your helpful collaborator has emailed you a ‘tar’ file (a 'tape archive' or in modern times, simply a packaged directory) of scripts to use to analyse the data. 

This file should have been emailed to you via Eventbrite. Please download the ***dogScripts.tar.gz*** file to your local computer for your email. Do not unpack it just yet. You can also download it from here: [https://cloudstor.aarnet.edu.au/plus/s/aV5uHrWzJ9PNZHj](https://cloudstor.aarnet.edu.au/plus/s/aV5uHrWzJ9PNZHj/download)

This local file needs to be transferred to the Artemis HPC. This can be done via a Graphical User Interface (GUI) tool (i.e. “point and click”) such as [FileZilla](https://filezilla-project.org/) or [WinSCP](https://winscp.net/eng/download.php), or via the command line. You may choose whichever method you prefer. Please note: if you choose to install FileZilla, ensure to UNSELECT the sneaky inclusion of any bloatware during the installation!

Note for Windows users: if you would prefer to use command line rather than install a GUI, you need to use a *Nix command line, NOT the Windows Command Prompt. If you have Windows 10, you can [install Ubuntu](https://tutorials.ubuntu.com/tutorial/tutorial-ubuntu-on-windows#0) from the Microsoft store. Or any version of Windows can use [Cygwin](https://www.cygwin.com/).  

Note for Mac users: you can use your Mac terminal app. Keep your Artemis session open, and open a new Mac terminal for your local session. It is often convenient to work with multiple environments open at the same time.

### Instructions for using FileZilla to copy a local file to Artemis:

Open FileZilla. 

In the 'Host' field, enter:
```
sftp://hpc.sydney.edu.au
``` 
In the Username field, enter your training login/unikey:
```
ict_hpctrain<N>
``` 
In the ‘Password’ field, enter the training password.

In the ‘Port’ field, you can leave it blank (default is 22).
Then click ‘Quick connect’. 
You will be prompted about saving passwords, you can choose whether or not to do this. When you are logged on, you should see the following message printed in the top panel
~~~
Status:    Directory listing of "/home/ict_hpctrain<N>" successful
~~~
{: .output}


<figure>
  <img src="{{ page.root }}/fig/pic03_filezilla.PNG" style="margin:10px;width:600px"/>
  <figcaption> The left-most two panels display your local computer’s filesystem. The right two panels are your connection to the Artemis filesystem. You can navigate the directory tree by expanding the yellow folders with your mouse, or typing the full directory pathname into the “Local site” or “Remote site” fields. Note that Windows use ‘\’ and Linux uses ‘/’ to separate directories. 
</figcaption>
</figure><br>


Before initiating the upload to Artemis, open the ‘destination’ location. This will be your working directory for today inside the ‘Training’ project. 

In the ‘Remote site’ field, type:

```
/project/Training/<yourDirectoryName>
```

then press enter. Now that your destination directory is open and ready to receive the upload, locate the ```dogScripts.tar.gz``` file on the local host (left panel) (it may be in your Downloads folder?).

To upload the file to Artemis, you can use any of the following methods:

 * -Double click the file
 * -Right click the file then select ‘Upload’
 * -Drag and drop the file from the left (source) to the right (destination)

As you can see, FileZilla is very simple to use. It can be used just as easily to transfer files from Artemis to your local computer, by simply initiating the transfer from the right (source=Artemis) to the left (destination=local computer). 


### Instructions for using command line ‘scp’ to copy a local file to Artemis:

First, change into the directory that contains the data you want to transfer (or else you will need to prepend the full pathname in front of the file name). 

The syntax for scp is
```
scp <user@host:file> <user@host:to> 
```


Since the file to be transferred is local, you do not need to include user@host. Run the below command **from a local terminal window** to copy the scripts archive to your working directory on Artemis:

~~~
scp dogScripts.tar.gz  ict_hpctrain<N>@hpc.sydney.edu.au:/project/Training/<yourDirectoryName>
~~~
{: .bash}
 
Done. Now that file is on Artemis in the folder you have uploaded it to.


# Check the file uploaded and unpack it

Now go back to your **remote terminal connected to Artemis** and run the following commands to untar the archive, move the scripts, and delete the archive and empty directory:

~~~
mkdir /project/Training/<yourDirectoryName>
cd /project/Training/<yourDirectoryName> 
tar -zxvf dogScripts.tar.gz 
mv dogScripts/* . 
rmdir dogScripts 
~~~
{: .bash}


