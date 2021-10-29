---
description: Hrflow.ai profile education JSON object.
---

# Education JSON

Education is way to describe the profile's academic background, it contains general information like location, date start/end and details information such as description / title.

## The Education Object

```python
{
     'content_uid': 'content_uid',
     'title': 'Mathematicien',
     'school': 'University',
     'description': 'Education description',
     'date_start': {
                    'iso8601': '2016-01-01T00:00:00',
                    'text': '2016-01-01',
                    'timestamp': 1451602800},
     'date_end': {
                  'iso8601': '2018-01-01T00:00:00', 
                  'text': '2018-01-01', 
                  'timestamp': 1514761200},
     'location': {'geojson': {'category': null,
                          'city': null,
                          'city_district': null,
                          'country': null,
                          'country_region': null,
                          'entrance': null,
                          'house': null,
                          'house_number': null,
                          'island': null,
                          'level': null,
                          'near': null,
                          'po_box': null,
                          'postcode': null,
                          'road': null,
                          'staircase': null,
                          'state': null,
                          'state_district': null,
                          'suburb': null,
                          'unit': null,
                          'world_region': null},
              'lat': null,
              'lng': null,
              'text': null},
     'certifications': [{
        'name': 'certificate edu',
        'value': null
    }],
     'courses': [{
        'name': 'cours edu',
        'value': null
    }],
     'tasks': [{
        'name': 'tache edu',
        'value': null
    }]
}
```

## Attributes

| name | description |
| :--- | :--- |
| content\_uid | The education's content uid |
| title | The education's title |
| school | The education's school |
| description | The education's description |
| date\_start | The education's start date as [date](../trait-objects/date-object.md) object |
| date\_end | The education's end date as [date](../trait-objects/date-object.md) object |
| location | The education's location as [location](../trait-objects/location-object.md) object |
| certifications | A list of education's [Certifications](https://developers.hrflow.ai/hr-json/trait-objects/certification-object) object |
| courses | A list of education's [Courses](https://developers.hrflow.ai/hr-json/trait-objects/course-object) object |
| tasks | A list of education's [Tasks](https://developers.hrflow.ai/hr-json/trait-objects/task-object) object |
| skills | A list of education's [Skills](https://developers.hrflow.ai/hr-json/trait-objects/skill-object) object |

