---
title: "Summary"
teaching: 5
exercises: 0
questions:
objectives:
- "Summarise RDS and HPC"
keypoints:
- "Lots of tools and ways to interface HPC/RDS"
- "Use whatever works for you!"
---

# Catch up summary

If you get lost at all, these few lines should log you on and get all the data required for any of the steps.

```
ssh ict_hpctrain<N>@hpc.sydney.edu.au
cd /rds/PRJ-Training
mkdir MyDirectory
cd MyDirectory
wget -O dogScripts.tar.gz https://cloudstor.aarnet.edu.au/plus/s/aV5uHrWzJ9PNZHj/download
tar -zxvf dogScripts.tar.gz 
mv dogScripts/* .
wget https://biomirror.mirror.ac.za/ncbigenomes/Canis_familiaris/CHR_05/cfa_ref_CanFam3.1_chr5.fa.gz
gunzip cfa_ref_CanFam3.1_chr5.fa.gz 
```

# Other Research Data storage options

The University has access to several platforms that are useful for storing/transferring/serving research data.

* Dropbox
* Cloudstor
* Microsoft OneDrive/SharePoint/Office365
* GitHub
* eNotebooks
* Pawsey/NCI
* Commerical Cloud
* ICT hosted virtual machines

See here for more info: https://sydney.edu.au/research/facilities/sydney-informatics-hub/digital-research-infrastructure.html


# Wrap up 

Thank you all for your attendance and participation. You have an idea of what methods can be used to transfer data between RDS, Artemis HPC, web and your local computer.  

Please feel free to contact us with any questions: [sih.info@sydney.edu.au](mailto:sih.info@sydney.edu.au)

We welcome your feedback, please complete the brief survey: [survey](https://redcap.sydney.edu.au/surveys/?s=FJ33MYNCRR&training=11&training_date=2021-03-26)

Check out the online documentation for more information:
[https://sydneyuni.atlassian.net/wiki/spaces/RC/overview](https://sydneyuni.atlassian.net/wiki/spaces/RC/overview)

***Reminder: Artemis is not backed up!***

<figure>
  <img src="{{ page.root }}/fig/artemisbackup.png" style="margin:10px;width:600px"/>
  <figcaption> Caption 
</figcaption>
</figure><br>




<br>
