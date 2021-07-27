---
description: Most frequently asked questions.
---

# F.A.Q

## What are profile tags, and how should I use them ?

A profile tag is an extra information associated with a **profile**.  
Profile tags helps users mark certain profiles with specific information for search, analytics or workflow filtering.

### How to format tags

You can add a list of searchable tags to a given profile,

* Each tag is defined by **name** and **value,**
* Value can be one of these data types  \(ie string, integer, float, boolean\).

Example:  
\[{"name": "blacklist", "value": False}, {"name": "url", "value": xxx}....\]

{% hint style="info" %}
Tags must be included at profile's creation.
{% endhint %}

## Profile unicity ?

An HrFlow Profile/Parsing object is unique by its **key** and **source\_key**.

The couple \(source\_key, key\) is mandatory to retrieve Profile/Parsing object.

## How to create a job application for a given profile ?

To add an application to a HrFlow profile, simply add the tag with the name 'application-board-job-key' and the value is 'board\_key-job\_key', the board key and the job key being the unique identifiers of corresponding HrFlow job.

Example:  
{"name": "application-board-job-key", "value": "b3cq584sqs4dvg456gddrfcsss-47dert596f6g95f3c1x2c"}

