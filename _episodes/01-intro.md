---
title: "Data transfer and RDS for HPC"
teaching: 20
exercises: 5
questions:
- "What is the Reasearch Data Store?"
objectives:
- "Connect to Artemis"
- "Create a new folder"
- "Change directory to your new folder"
keypoints:
- "Recall the difference between _Classic_ and _RCOS_ and _nextgen_ RDS"
- "Recall how to connect to Artemis HPC"
---
This episode introduces the Research Data Storage options available at the University of Sydney, and how we can interface and interact with them.


# What is the Research Data Store?

Artemis is not backed up. Its hardware is geared towards processing. We have a dedicated set of machines for safe data storage, collectively referred to as the Research Data Store [RDS](https://sydneyuni.atlassian.net/wiki/spaces/RC/pages/228589620/Research+Data+Store). RDS has two legacy “flavours”: ***Research Computing Optimised Storage (RCOS)*** and ***‘Classic’ RDS***. While the names differ, they are both RDS, both backed up, and both linked to a project via the Researcher Dashboard (DashR). Each project in [DashR](https://dashr.sydney.edu.au/) will detail your RDS service.



***RCOS*** is a Linux-style (NFS) data storage service, accessible via SFTP from an RCOS server. You can also access RCOS from an Artemis session, as RCOS is ‘mounted’ (appears as an accessible drive) on the Artemis HPC. Data can thus be easily moved between RCOS and Artemis using a variety of methods such as ‘cp’, ‘scp’, ‘rsync’ etc. However, RCOS is not easily network accessible on Windows and OSX. So if you have data on RDS that you need to access via an application on your local computer, it can be harder to do this with RCOS. 

***Classic RDS*** is a Windows-style (CIFS) data storage service accessible as a network drive on Windows, Mac and Linux systems. Network accessibility is handy if you often access your RDS data locally. You can read RDS data into local applications, or easily drag and drop files between your local hard drive (or USB/external hard drive) and classic RDS. Transfer of data between ‘classic’ RDS and Artemis is more difficult, and thus not the recommended data storage option for you if you are a frequent HPC user or work with large datasets.

~~ICT will be implementing a more seamless RDS in the future!~~ ICT has implemented a seamless RDS comprising the benefits of both Classic and RCOS systems (called ***NextGen RDS**)

Check out the online documentation for more information:
[https://sydneyuni.atlassian.net/wiki/spaces/RC/overview](https://sydneyuni.atlassian.net/wiki/spaces/RC/overview)


# Practicing Data Transfer

There are a lot of data transfer tools and tricks out there, and which you use depends on where you want to move to and from (e.g. from your local computer to Artemis, from Artemis to RDS, etc) as well as your own personal preferences. Today you will gain an understanding of how to choose a good method, and gain practice in some of these methods following a ‘case study’ approach. 

**Case study**:You are an animal genetics researcher (student/post-doc/professor). You have performed some genome sequencing on a new dog sample which has an inherited disease, and need to analyse the data ASAP and send the results to your collaborator to present at a conference next week. The files you need are in assorted locations, but you need to get them all on to Artemis for processing. And of course, back them all up on to the RDS!


# Setup

If you are not already connected to Artemis, please establish a connection now. Mac users can use their native terminal app, Windows users will need a shell emulator. Please see the software [setup instruction here]({{ page.root }}/setup) and the [Connecting to Artemis section here](https://sydney-informatics-hub.github.io/training.artemis.introhpc/01-intro/index.html)

Even if you have your own Artemis and/or RDS account, please use our training unikeys/logins for the day. If you have not yet been assigned one, please let one of our staff know. These logins are

```
ict_hpctrain<N>
```

where N is a number between 1 and 40. Each user today will have a different number, and be members of the same DashR project called ‘Training’. Note: whenever you see the angle brackets, this means “replace the brackets AND their contents with the relevant content to you”. 

~~~
ssh ict_hpctrain<N>@hpc.sydney.edu.au
~~~
{: .bash}

Once you are connected to Artemis, make a directory for yourself to work in within the /project/Training directory. Call it something unique (not just “training”) and memorable. Please do not include spaces, and remember that CASE MATTERS very much on Linux systems. 

Make your directory

~~~
mkdir /project/Training/<yourDirectoryName>
~~~
{: .bash}

Then change into it:

~~~
cd /project/Training/<yourDirectoryName> 
~~~
{: .bash}

<br>
