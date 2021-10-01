---
description: >-
  What is the mechanism used in HrFlow.ai to add link a given profile that
  applies to a job ?
---

# How to attach a job application to a profile ?

To attach an application to a HrFlow.ai profile, simply add the tag with :

* name **: application\_boardKey\_jobReference**
*  value : **hash1**\_**hash2, where hash1 and hash2 are respectively** the board key and the job reference 

You can also add another optional tag, if you use our searching API and have access to the **job\_key** \(which is another identifier to a job in HrFlow.ai\), with : 

* name **: application\_boardKey\_jobKey**
*  value : **hash1**\_**hash3, where hash1 and hash2 are respectively** the board key and the job key 

These tags as all tags should be created and included at profile creation, linking it to the corresponding job.

