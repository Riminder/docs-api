---
description: Hrflow.ai label JSON object.
---

# Label JSON

Label object contains information about profile stage, or rating for a given job, stage's value is one of \['new', 'yes', 'no', 'later'\] and ratings represents the user's assessment based on object quality and performance

## The Label Object

```python
{

    'job_key': 'job_key',
    'job_reference': 'job_reference'
    'board_key': 'board_key',
    'stage': 'yes',
    'date_stage': 1622728952213,
    'rating': 0.6,
    'date_rating': 1622728952213,

}
```

## Attributes

| name | description |
| :--- | :--- |
| job\_key | The Job's key that you want to record the stage |
| job\_reference | The Job's reference |
| stage | The stage \(ie. yes, no, later, new\) for the given job |
| rating | The profile's rating for the given job |
| date\_stage | Time at which the stage was last updated |
| date\_rating | Time at which the rating was last updated |

