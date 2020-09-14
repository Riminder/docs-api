# Label
Label object represents a simple way to track all profile's application and their 
stage (yes/no/later/new). If no record is present, so all 
  
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
| job_key | The Job's key that you want to record the stage |
| job_reference | The Job's reference |
| stage | The stage (ie. yes, no, later, new) for the given job |
| rating | The profile's rating for the given job |
| date_stage | Time at which the stage was last updated |
| date_rating | Time at which the rating was last updated |
