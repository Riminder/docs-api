# Parsing object

## Parsing

This is a complete object containing **Parsing** results, it details all detected entities on a document.

It helps data scientist to further in their studies and enhance the quality of their analysis.

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
| content\_uid | The object's content uid |
| key | Unique identifier for the object |
| file name | The original uploaded file name |
| file size | The original uploaded file size |
| persons | A list of all parsed [Persons](https://developers.hrflow.ai/hr-json/profile-objects/person-object) |
| emails | This field records all existing emails in a document. |
| phones | This field records all parsed phones from a document. |
| location | The Profile's [Location](https://developers.hrflow.ai/hr-json/trait-objects/location-object) object |
| images | A list of URLs for all detected images |
| picture | The url of profile's picture |
| urls | The urls for: linkedin / twitter / facebook / github if they exist |
| gender | The Profile's gender |
| driving licence | The Profile's driving licence if exits otherwise the default value is null |
| summary | The Profile's summary |
| text | The Profile's text, it contains a long resume   of a profile, it is generated based on parsed text |
| text language | The original language of the document |
| educations | A list of [Education](https://developers.hrflow.ai/hr-json/profile-objects/education-object) object |
| eductions\_duration | Education's duration |
| experiences | A list of [Experience](https://developers.hrflow.ai/hr-json/profile-objects/experience-object) object |
| experiences\_duration | Experience's duration, it calculates profile's seniority |
| skills | A list of profile's [Skill](https://developers.hrflow.ai/hr-json/trait-objects/skill-object) object |
| languages | A list of profile's [Language](https://developers.hrflow.ai/hr-json/trait-objects/language-object) object |
| interests | A list of profile's [Interest](https://developers.hrflow.ai/hr-json/profile-objects/interest-object) object |

