# Experience object

Experience is way to describe the profile's career path, it contains general information about location, date start/end and detailed description / title as it is parsed.

## The Experience Object

```python
{              
      'content_uid': 'content_uid',
      'title': 'Data scientist'
      'company': 'Mathematic Departement',
      'description': 'Experience s description',
      'date_start': {'iso8601': '2018-01-01T00:00:00',
                     'text': '2018-01-01',
                     'timestamp': 1467324000},
      'date_end': {'iso8601': '2018-07-01T00:00:00',
                   'text': '2018-07-01',
                   'timestamp': 1530396000},
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
                   'text': null}
}
```

## Attributes

| name | description |
| :--- | :--- |
| content\_uid | The experience's content uid |
| title | The experience's title |
| company | The experience's school |
| description | The experience's description |
| date\_start | The experience's date start as [date](https://developers.hrflow.ai/hr-json/profile-objects/date-object) object |
| date\_end | The experience's date end as [date](https://developers.hrflow.ai/hr-json/profile-objects/date-object) object |
| location | The experience's location as [location](https://developers.hrflow.ai/hr-json/profile-objects/location-object) object |

