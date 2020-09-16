# Skill object

Skill describes a detected expertise. Our AI algorithm further tag the skill with 
a hard (for hard skills) or soft (for soft skill) type.


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
| value | The skill's value, it measures the confidence level of expertise|

