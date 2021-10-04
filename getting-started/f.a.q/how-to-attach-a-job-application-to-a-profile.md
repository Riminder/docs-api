---
description: >-
  What is the mechanism used in HrFlow.ai to add link a given profile that
  applies to a job ?
---

# How to attach a job application to a profile ?

To attach an application to a HrFlow.ai profile, simply add the tag with :

* name **: application\_boardKey\_jobReference**
*  value : **hash1**\_**hash2, where hash1 and hash2** are respectively the **board key** and the **job reference** 

Note that a board must be created for each source of job offers, even if job offers aren't indexed in HrFlow.ai.

Here is an example that illustrates how to link a profile to a job with reference _REFXC23A_  that belongs to the board _44d6ght66436a852baf13980c3da4041fa3f0876 :_ 

```text
{..., 
"tags": [{"name": "application_boardKey_jobReference",
          "value": "44d6ght66436a852baf13980c3da4041fa3f0876_REFXC23A"}], ... }
```

You can also add another optional tag, if you use our searching API and have access to the **job\_key** \(which is another identifier to a job in HrFlow.ai\), with : 

* name **: application\_boardKey\_jobKey**
*  value : **hash1**\_**hash3, where hash1 and hash2 are respectively** the board key and the job key 

These tags as all tags should be created and included at profile creation, linking it to the corresponding job.

```text
{..., 
"tags": [{"name": "application_boardKey_jobReference",
          "value": "44d6ght66436a852baf13980c3da4041fa3f0876_REFXC23A"},
         {"name": "application_boardKey_jobKey",
          "value": "44d6ght66436a852baf13980c3da4041fa3f0876_xxcdht6643fgh65vhb13980c3da4041f"}], ... }
```

