# Education

This is a complete object that contains **Parsing** results, it details
 detected entities by our algorithm such dates and locations as they have 
 been in the document, it helps data scientist to go further in their studies.
 
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
| content\_uid | The education's content_uid |
| key | Unique identifier for the object |
| title | The original uploaded file name |
| school | The original uploaded file size |
| description | A list of all parsed full names |
| date_start | A list of all parsed emails |
| date_end | A list of all parsed phones |
| location | Location as detected in the document, it contains the original text|
