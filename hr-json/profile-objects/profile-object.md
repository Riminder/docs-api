# Profile object

## Profile

The Profile object is a standard representation of a candidate, it is based on 
Parsing profile
 
| **ENDPOINTS** |
| :--- |
| [**POST** /v1/profile/indexing](https://developers.hrflow.ai/api-reference/profile-api/post-profile-indexing) |
| [**PUT** /v1/profile/indexing](https://developers.hrflow.ai/api-reference/profile-api/put-profile-indexing) |
| [**GET** /v1/profile/indexing](https://developers.hrflow.ai/api-reference/profile-api/get-profile-indexing) |

## The Profile Object

```python
{   'id': 'profile_id',
    'key': 'profile_key',
    'reference': 'profile_reference',
    'archive': null,
    'consent_algorithmic': {'controller': {'embedding': true,
                                            'parsing': true,
                                            'reasoning': false,
                                            'revealing': false,
                                            'scoring': true,
                                            'searching': false},
                                 'owner': {'embedding': true,
                                           'parsing': true,
                                           'reasoning': false,
                                           'revealing': false,
                                           'scoring': true,
                                           'searching': false}},
    'source': {'id': 'source_id',
            'key': 'source_key',
            'name': 'async source',
            'subtype': 'http',
            'type': 'api'},
    'updated_at': '2020-09-11T10:26:36+0000',
    'created_at': '2020-08-06T10:09:47+0000',
    'info': {'email': 'harry.potter@gmail.com',
              'first_name': 'Harry',
              'full_name': 'Harry Potter',
              'gender': 'male',
              'last_name': 'Potter',
              'location': {'fields': [],
                           'gmaps': null,
                           'lat': null,
                           'lng': null,
                           'text': null},
              'phone': '0202',
              'picture': null,
              'summary': 'Brief summary',
              'urls': {'facebook': '',
                       'from_resume': [],
                       'github': '',
                       'linkedin': '',
                       'picture': '',
                       'twitter': ''}},
    'text': 'Profile s text',
    'text_language': 'en',
    'educations': [{ 'key': 'education_key',
                     'title': 'Mathematicien',
                     'school': 'University',
                     'description': 'Education s description',
                     'date_start': '2016-01-01T00:00:00',
                     'date_end': '2018-01-01T00:00:00',
                     'location': {'fields': [],
                                  'gmaps': null,
                                  'lat': null,
                                  'lng': null,
                                  'text': 'Scotland'},
                     'hard_skills': [],
                     'soft_skills': []}],
    'educations_duration': 2,
    'experiences': [{ 'key': 'experience_key',
                      'title': 'Data scientist',
                      'company': 'Mathematic Departement',
                      'description': 'Experience s description.',
                      'date_start': '2018-01-01T00:00:00',
                      'date_end': '2018-07-01T00:00:00',
                      'location': {'fields': [],
                                   'gmaps': null,
                                   'lat': null,
                                   'lng': null,
                                   'text': 'Paris'},
                      'hard_skills': [],
                      'soft_skills': []}],
    'experiences_duration': 0.7,
    'attachments': [],
    'skills': [{'name': 'manual skill', 'value': null},
                {'name': 'Creative spirit', 'value': null},
                {'name': 'Writing skills', 'value': null},
                {'name': 'Communication', 'value': null}],
    'languages': [{'name': 'english', 'value': null}],
    'interests': [{'name': 'football', 'value': null}],
    'labels': [{'job_key': 'job_key', 'stage': 'yes'}],
    'tags': [{'name':'archive', 'value': true}],
    'metadatas': []}
```

## Attributes

| name | description |
| :--- | :--- |
| id | The document's content_uid |
| key | Unique identifier for the object |
| reference | The profile's reference |
| archive | The date when a profile is archived, if the profile is not archived archive will be null  |
| consent\_algorithmic | A list of all parsed full names |
| source | The source object |
| updated_at | Time at which the object was last updated |
| created_at | Time at which the object was created |
| info | The Profile's info object  |
| text_language | The original language of Profile's attached document |
| text | The Profile's text |
| experiences_duration | The Profile's gender |
| educations_duration | The Profile's parsed driving licence if exits  |
| experiences | A list of profile's experience object |
| educations | A list of profile's education object |
| attachments | A list of profile's attachment object |
| skills | A list of Object skill |
| languages | AA list of Object language |
| interests | A list of Object interest |
| labels | A list of label object that you can attach to an object |
| tags | A list of tag object that you can include with an object, This can be helpful in attaching tags to a profile |
| metadatas | A list of metadata object that you can include with an object. This can be useful for storing additional information about the object in a structured format|
