# Education object

Education is way to describe the profile's academic background, it contains 
general information about location, date start/end and detailed information such as
description / title.

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
              'text': null}
}
```

## Attributes

| name | description |
| :--- | :--- |
| content\_uid | The education's content uid |
| title | The education's title |
| school | The education's school |
| description | The education's description |
| date\_start | The education's date start as [date](https://developers.hrflow.ai/hr-json/profile-objects/date-object) object |
| date\_end | The education's date end as [date](https://developers.hrflow.ai/hr-json/profile-objects/date-object) object |
| location | The education's location as [location](https://developers.hrflow.ai/hr-json/profile-objects/location-object) object |

