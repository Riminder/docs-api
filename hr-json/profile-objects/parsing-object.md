# Parsing object

## Parsing

This is a complete object that contains **Parsing** results, it details
 detected entities by our algorithm such dates and locations as they have 
 been in the document, it helps data scientist to go further in their studies.
 
| **ENDPOINTS** |
| :--- |
| \*\*\*\*[**POST** /v1/profile/parsing/file](https://developers.hrflow.ai/api-reference/profile-api/post-profile) |
| \*\*\*\*[**GET** /v1/profile/parsing](https://developers.hrflow.ai/api-reference/profile-api/get-profile-parsing) |

## The Parsing Object

```python
{
      'content_uid': 'content_uid', 
      'key': 'profile_key',
      'file_name': 'filename.pdf',
      'file_size': null, 
      'persons': [{'full_name': 'Harry Potter', 
                   'first_name': 'Harry',
                   'last_name': 'Potter'}],
      'emails': ['harry.potter@gmail.com'],
      'phones': ['0202'],
      'location': {
           'text': '803 Green Lane London N07 8MA',
           'lat': 51.581551, 
           'lng': -0.099649, 
           'geojson': {
              'house': null, 
              'category': null, 
              'near': null, 
              'house_number': 803, 
              'road': 'Green Lane', 
              'unit': null, 
              'level': null, 
              'staircase': null, 
              'entrance': null, 
              'po_box': null, 
              'postcode': null, 
              'suburb': null, 
              'city_district': null, 
              'city': 'London', 
              'island': null, 
              'state_district': null, 
              'state': null, 
              'country_region': null, 
              'country': 'UK', 
              'world_region': null}}, 
     'images': null, 
     'picture': 'https://riminder-documents-eu-2019-12.s3-eu-west-1.amazonaws.com/picture.png',
     'urls': [
              {'type': 'from_resume', 'url': []}, 
              {'type': 'linkedin', 'url': null}, 
              {'type': 'twitter', 'url': null}, 
              {'type': 'facebook', 'url': null}, 
              {'type': 'github', 'url': null}],
     'gender': 'male',
     'driving_licence': null, 
     'summary': 'Brief summary', 
     'text': 'Profile s text' ,
     'text_language': 'en'
     'educations': [
                    {'content_uid': 'content_uid',
                     'date_end': {
                                  'iso8601': '2018-01-01T00:00:00', 
                                  'text': '2018-01-01', 
                                  'timestamp': 1514761200},
                     'date_start': {
                                    'iso8601': '2016-01-01T00:00:00',
                                    'text': '2016-01-01',
                                    'timestamp': 1451602800},
                     'description': 'Education description',
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
                 'school': 'University',
                 'title': 'Mathematicien'}
               ],
 'educations_duration': 2,
 'experiences': [
                 {'content_uid': 'content_uid',
                  'company': 'Mathematic Departement',
                  'date_end': {'iso8601': '2018-07-01T00:00:00',
                               'text': '2018-07-01',
                               'timestamp': 1530396000},
                  'date_start': {'iso8601': '2018-01-01T00:00:00',
                                 'text': '2018-01-01',
                                 'timestamp': 1467324000},
                  'description': 'Experience s description',
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
                  'title': 'Data scientist'}],
 'experiences_duration': 0.7,
 'skills': [{'name':'manual skill', 'type': 'hard', 'value': null},
            {'name':'Creative spirit', 'type': 'soft','value': null}, 
            {'name':'Writing skills', 'type': 'hard','value': null}, 
            {'name':'Communication', 'type': 'soft','value': null}],
 'languages': [{'name':'english', 'value': null}],
 'interests': [{'name':'football', 'value': null}]
 }
```

## Attributes

| name | description |
| :--- | :--- |
| content\_uid | The document's content_uid |
| key | Unique identifier for the object |
| file name | The original uploaded file name |
| file size | The original uploaded file size |
| persons | A list of all parsed Persons |
| emails | A list of all parsed emails |
| phones | A list of all parsed phones |
| location | The Profile's location object|
| images | All detected images  |
| picture | An url for parsed profile's picture |
| urls |  |
| gender | The Profile's gender |
| driving licence | The Profile's parsed driving licence if exits unless it is set to null  |
| summary | The Profile's parsed summary |
| text | The Profile's parsed text |
| text language | The profile's document original language  |
| experiences | A list of experience object |
| experiences\_duration | Experience's duration |
| educations | A list of Object education |
| eductions\_duration | Education's duration |
| skills | The profile's parsed skills |
| languages | The profile's parsed languages |
| interests | The profile's parsed interests |

