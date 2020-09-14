# Label object

Label object represents a simple way to track all profile's application and their stage \(yes/no/later/new\). If no record is present, so all

## The Label Object

```python
{
    'job_key':'job_key',
    'job_reference': 'ref1',
    'stage':'yes',
    'rating': 0.6,
    'date_stage':'2020-09-15T21:59',
    'date_rating': '2020-10-15T21:59',
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

