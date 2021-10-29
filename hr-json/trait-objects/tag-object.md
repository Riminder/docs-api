---
description: Hrflow.ai tag JSON object.
---

# Tag JSON

Tag helps to mark objects (profile/job) and allows to segment these objects into different categories.

Tags can be used to search and filter objects. This is why they should only contain short information that helps classify your database.

For example, a tag could contain a job id or category, a user IP, or just a boolean variable. But it should not contain a comment.

A good practice for naming tags' variables is using a **snake case **(replacing spaces with underscores and writing the first letter of each word written in lowercase). \
For example, "**website\_user\_ip" **or** "job\_key"**.

## The Tag Object

```python
{
    'name':'example',
    'value': true
}
```

## Attributes

| name  | description     |
| ----- | --------------- |
| name  | The tag's name  |
| value | The tag's value |
