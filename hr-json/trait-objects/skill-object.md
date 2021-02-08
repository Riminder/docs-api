---
description: Hrflow.ai skill JSON object.
---

# Skill JSON

Skill describes a detected expertise. Our AI algorithms classify skills to two types:

* **hard** for hard skills
* **soft** for soft skill

## The Skill Object

```python
{
    'name':'python',
    'type': 'hard',
    'value': 1
}
```

## Attributes

| name | description |
| :--- | :--- |
| name | The skill's name |
| type | The skill's type : either hard or soft |
| value | The skill's value, it measures the confidence level of expertise |

