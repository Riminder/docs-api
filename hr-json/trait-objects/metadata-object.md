---
description: Hrflow.ai metadata JSON object.
---

# Metadata JSON

Metadata is a set of extra data attached to an object that gives additional information in order to include a more accurate description of the object.

Contrary to Tags, Metadata are not searchable. They can be used to include comments or additional information in the profile or job object.

Similar to tags, a good practice for naming variables in metadata objects is using a **snake case** \(replacing spaces with underscores and writing the first letter of each word written in lowercase\).   
For example, **"consultant\_comment"** or **"personal\_email"**.

## The Metadata Object

```python
{
    'name':'personal_email',
    'value': "harry.potter@gmail.com"
}
```

## Attributes

| name | description |
| :--- | :--- |
| name | The metadata's name |
| value | The metadata's value |

