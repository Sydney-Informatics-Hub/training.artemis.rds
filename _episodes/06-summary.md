---
title: "Summary and other Data Storage options"
teaching: 5
exercises: 0
questions:
- "What other Data Storage options are availble?"
objectives:
- "Summarise RDS and HPC"
- "List the other Data Storage options availble."
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

* ~~Dropbox~~
* ~~[AARNet Cloudstor](https://cloudstor.aarnet.edu.au/)~~
* Microsoft OneDrive/SharePoint/Office365
* [GitHub Enterprise](https://github.sydney.edu.au/)
* [eNotebooks](https://sydneyuni.service-now.com/sm?id=kb_article_view&sysparm_article=KB0013721&sys_kb_id=d247761f874545106569cae20cbb35d9&spa=1)
* [Pawsey](https://pawsey.org.au/) / [NCI](https://nci.org.au/)
* Commerical Cloud (AWS, Ronin, GCP, Azure, etc)
* [ICT hosted virtual machines](https://sydneyuni.service-now.com/sm?id=kb_article_view&sysparm_article=KB0010875)

See [Service-Now Knowledge Article](https://sydneyuni.service-now.com/sm?sys_kb_id=c197f25f874545106569cae20cbb3507&id=kb_article_view&sysparm_rank=1&sysparm_tsqueryId=50122eb5db30155067530793f39619a3) for more information.


# Wrap up 

Thank you all for your attendance and participation. You have an idea of what methods can be used to transfer data between RDS, Artemis HPC, web and your local computer.  

Please feel free to contact us with any questions: [sih.info@sydney.edu.au](mailto:sih.info@sydney.edu.au)

We welcome your feedback, please complete the brief survey: [survey](https://redcap.sydney.edu.au/surveys/?s=FJ33MYNCRR&training=11)

Check out the online documentation for more information:
[https://sydneyuni.atlassian.net/wiki/spaces/RC/overview](https://sydneyuni.atlassian.net/wiki/spaces/RC/overview)

***Reminder: Artemis is not backed up!***

<figure>
  <img src="{{ page.root }}/fig/05_backup.png" style="margin:10px;width:600px"/>
  <figcaption> Caption 
</figcaption>
</figure><br>




<br>
