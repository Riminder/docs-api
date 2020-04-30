---
description: Most frequently asked questions
---

# F.A.Q

## What are profile tags, and how should I use them?

A profile tag is an extra information associated with a **profile**.   
Profile tags helps users mark certain profiles with specific information for search, analytics or workflow filtering.

#### How to format tags

You can add a list of searchable tags to a given profile, 

* Each tag is defined by **name** and **value,**
* Value can be one of these data types  \(ie string, integer, float, boolean\).

Example:  
                              \[{"name": "blacklist", "value": False}, {"name": "url", "value": xxx}....\]

{% hint style="info" %}
Tags must be included at profile's creation.
{% endhint %}

## What is an item\_id and a profile\_id?

An Item ID \[item\_id\] is an attribute used to identify all documents uploaded in hrflow \(either job's item or profile's item\).

  
A Profile ID \[profile\_id\] is a unique identifier for a **HrFlow Profile.**

{% hint style="info" %}
Profile Id and Source Id represent in a unique way HrFlow Profile
{% endhint %}

## Profile unicity ?

An  HrFlow profile is unique by its **profile\_id** and **source\_id**.

The couple \(source\_id, profile\_id\) is mandotory to retreive Profile's parsing / embedding / metadata ...

