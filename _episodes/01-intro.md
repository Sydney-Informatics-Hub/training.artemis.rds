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

Artemis is not backed up. Its hardware is geared towards processing. We have a dedicated set of machines for safe data storage, collectively referred to as the Research Data Store [RDS](https://sydneyuni.atlassian.net/wiki/spaces/RC/pages/228589620/Research+Data+Store). 

RDS has two legacy “flavours”: ***Research Computing Optimised Storage (RCOS)*** and ***‘Classic’ RDS***. They were both amalgamted into the ***Nextgen RDS*** in 2021 simply referred to now as ***The RDS***, but you may see references to them in some documentation. Access to RDS is granted and managed through a "Research Data Managment Plan" project completed in the [Research Dashboard (dashr)](https://dashr.sydney.edu.au/).

The RDS file server that can be mounted on Windows, MacOS, and Linux using a variety of protocols. On Linux-style systems it is accessible via `sftp`, `scp`,  or from an Artemis session, as RDS is ‘mounted’ (appears as an accessible drive) on the Artemis HPC. Data can thus be easily moved between RDS and Artemis using a variety of methods such as ‘cp’, ‘scp’, ‘rsync’ etc. On Windows, Mac and Linux systems the RDS may be mounted as a network drive using `SMB`. Then you may read RDS data into local applications, or easily drag and drop files between your local hard drive (or USB/external hard drive) and the RDS. 

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
