# Parsing object

## Parsing

This is a complete object containing **Parsing** results, it details all
 detected entities by our algorithm, it helps data scientist to go further
  in their studies and enhance the quality of their studies.
 
| **ENDPOINTS** |
| :--- |
| [**POST** /v1/profile/parsing/file](https://developers.hrflow.ai/api-reference/profile-api/post-profile) |
| [**GET** /v1/profile/parsing](https://developers.hrflow.ai/api-reference/profile-api/get-profile-parsing) |

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
                     'title': 'Mathematicien'                     
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
                              'text': null}}
               ],
     'educations_duration': 2,
     'experiences': [
                     {'content_uid': 'content_uid',
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
                        }],
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
| persons | A list of all parsed [Persons](https://developers.hrflow.ai/hr-json/profile-objects/person-object) |
| emails | A list of all parsed emails |
| phones | A list of all parsed phones |
| location | The Profile's [Location](https://developers.hrflow.ai/hr-json/profile-objects/location-object) object|
| images | All detected images  |
| picture | An url for parsed profile's picture |
| urls |  |
| gender | The Profile's gender |
| driving licence | The Profile's parsed driving licence if exits unless it is set to null  |
| summary | The Profile's parsed summary |
| text | The Profile's parsed text |
| text language | The original language of the document |
| educations | A list of [Education](https://developers.hrflow.ai/hr-json/profile-objects/education-object) object |
| eductions\_duration | Education's duration |
| experiences | A list of [Experience](https://developers.hrflow.ai/hr-json/profile-objects/experience-object) object |
| experiences\_duration | Experience's duration |
| skills | A list of profile's [Skill](https://developers.hrflow.ai/hr-json/profile-objects/skill-object) object |
| languages | A list of profile's [Language](https://developers.hrflow.ai/hr-json/profile-objects/language-object) object |
| interests | A list of profile's [Interest](https://developers.hrflow.ai/hr-json/profile-objects/interest-object) object |

