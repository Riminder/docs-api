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


## Profile unicity ?

An  HrFlow Profile/Parsing object is unique by its **key** and **source\_key**.

The couple \(source\_key, key\) is mandatory to retrieve Profile/Parsing object.

