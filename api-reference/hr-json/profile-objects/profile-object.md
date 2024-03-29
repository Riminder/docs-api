---
description: Hrflow.ai profile JSON object.
---

# Profile JSON

## Profile

The Profile object is a standard representation of a candidate, aims to improve Object Hr Management.

It is a faster / readable data structure helping developers to cover many Hr use cases.

The API allows you to create, update and retrieve your profile.

| **ENDPOINTS**                                                                                                 |
| ------------------------------------------------------------------------------------------------------------- |
| [**POST** /v1/profile/indexing](https://developers.hrflow.ai/api-reference/profile-api/post-profile-indexing) |
| [**PUT** /v1/profile/indexing](https://developers.hrflow.ai/api-reference/profile-api/put-profile-indexing)   |
| [**GET** /v1/profile/indexing](https://developers.hrflow.ai/api-reference/profile-api/get-profile-indexing)   |

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
    'info': { 'email': 'harry.potter@gmail.com',
              'first_name': 'Harry',
              'full_name': 'Harry Potter',
              'last_name': 'Potter',
              'date_birth': '1990-08-09T00:00:00+0000'
              'gender': 'male',
              'location': {'fields': {
                                "category": null,
                                "city": "Paris",
                                "city_district": "8e Arrondissement",
                                "country": "FRA",
                                "country_region": null,
                                "entrance": null,
                                "house": null,
                                "house_number": "18",
                                "island": null,
                                "level": null,
                                "near": null,
                                "po_box": null,
                                "postcode": "75008",
                                "road": "Rue Daru",
                                "staircase": null,
                                "state": "Ile-de-France",
                                "state_district": "Paris",
                                "suburb": "8e Arrondissement",
                                "text": "18 Rue Daru, 75008 Paris, France",
                                "unit": null,
                                "world_region": null
                            },
                           'gmaps': null,
                           'lat': null,
                           'lng': null,
                           'text': null},
              'phone': '0202',
              'picture': 'picture public url',
              'summary': 'Brief summary',
              'urls': [{
                        "type": "from_resume",
                        "url": []
                    },
                    {
                        "type": "linkedin",
                        "url": null
                    },
                    {
                        "type": "twitter",
                        "url": null
                    },
                    {
                        "type": "facebook",
                        "url": null
                    },
                    {
                        "type": "github",
                        "url": null
                    }]
    },
    'text': 'Profile s text',
    'text_language': 'en',
    'educations': [{ 'key': 'education_key',
                     'title': 'Mathematicien',
                     'school': 'University',
                     'description': 'Education s description',
                     'date_start': '2016-01-01T00:00:00',
                     'date_end': '2018-01-01T00:00:00',
                     'location': {'fields':  {
                                        'category': null,
                                        'city': 'Paris',
                                        'city_district': null,
                                        'country': 'FRA',
                                        'country_region': null,
                                        'entrance': null,
                                        'house': null,
                                        'house_number': null,
                                        'island': null,
                                        'level': null,
                                        'near': null,
                                        'po_box': null,
                                        'postcode': '75001',
                                        'road': null,
                                        'staircase': null,
                                        'state': 'Ile-de-France',
                                        'state_district': 'Paris',
                                        'suburb': null,
                                        'text': 'Paris, Ile-de-France, France',
                                        'unit': null,
                                        'world_region': null
                                  },
                                  'gmaps': null,
                                  'lat': null,
                                  'lng': null,
                                  'text': 'Scotland'},
                     'certifications': [{'name': 'certificate edu', 'value': null}],
                     'courses': [{'name': 'course edu', 'value': null}],
                     'tasks': [{'name': 'task edu', 'value': null}],
                     'skills': [{'name': 'skill edu', 'type' : 'hard', 'value': null}]
    }],
    'educations_duration': 2,
    'experiences': [{ 'key': 'experience_key',
                      'title': 'Data scientist',
                      'company': 'Mathematic Departement',
                      'description': 'Experience s description.',
                      'date_start': '2018-01-01T00:00:00',
                      'date_end': '2018-07-01T00:00:00',
                      'location': {'fields':  {
                                        "category": null,
                                        "city": "Saclay",
                                        "city_district": null,
                                        "country": "FRA",
                                        "country_region": null,
                                        "entrance": null,
                                        "house": null,
                                        "house_number": null,
                                        "island": null,
                                        "level": null,
                                        "near": null,
                                        "po_box": null,
                                        "postcode": "91400",
                                        "road": "Rue de Paris",
                                        "staircase": null,
                                        "state": "Ile-de-France",
                                        "state_district": "Essonne",
                                        "suburb": null,
                                        "text": "Rue de Paris, 91400 Saclay, France",
                                        "unit": null,
                                        "world_region": null
                                    },
                                   'gmaps': null,
                                   'lat': null,
                                   'lng': null,
                                   'text': 'Paris'},
                      'certifications': [{'name': 'certificate exp', 'value': null}],
                     'courses': [{'name': 'course exp', 'value': null}],
                     'tasks': [{'name': 'task exp', 'value': null}],
                     'skills': [{'name': 'skill exp', 'type' : 'hard', 'value': null}]
    }],
    'experiences_duration': 0.7,
    'attachments': [{
                      'alt': 'alt_resume',
                      'created_at': '2020-09-11T10:26:29+0000',
                      'extension': '.pdf',
                      'file_name': 'resume',
                      'file_size': 528305,
                      'original_file_name': 'resume',
                      'public_url': 'https://riminder-documents-eu-2019-12.s3-eu-west-1.amazonaws.com/resume.pdf',
                      'type': 'resume',
                      'updated_at': '2020-09-11T10:26:29+0000'},
                     {
                      'alt': 'alt_original',
                      'created_at': '2020-09-11T10:26:29+0000',
                      'extension': '.pdf',
                      'file_name': 'original',
                      'file_size': 537789,
                      'original_file_name': 'original',
                      'public_url': 'https://riminder-documents-eu-2019-12.s3-eu-west-1.amazonaws.com/original.pdf',
                      'type': 'original',
                      'updated_at': '2020-09-11T10:26:29+0000'}],
    'certifications': [
        {'name': 'certificate', 'value': null}
        ],
    'courses': [
        {'name': 'course', 'value': null}
        ],
    'tasks': [
        {'name': 'task', 'value': null}}
        ],
    'skills': [{'name': 'manual skill', 'value': null, 'type': 'hard'},
                {'name': 'Creative spirit', 'value': null, 'type': 'soft'},
                {'name': 'Writing skills', 'value': null, 'type': 'hard'},
                {'name': 'Communication', 'value': null, 'type': 'soft'}],
    'languages': [{'name': 'english', 'value': null}],
    'interests': [{'name': 'football', 'value': null}],
    'labels': [{'job_key': 'job_key', 'stage': 'yes'}],
    'tags': [{'name':'archive', 'value': true}],
    'metadatas': [{'name':'personal-email', 'value': 'harry.potter@gmail.com'}]}
```

## Attributes

| name                  | description                                                                                                                                                                                                                        |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                    | The object's id                                                                                                                                                                                                                    |
| key                   | Unique identifier for the object                                                                                                                                                                                                   |
| reference             | The profile's reference, it must be unique for a given source                                                                                                                                                                      |
| archive               | The date when a profile is archived, if the profile is not archived archive will be null                                                                                                                                           |
| consent\_algorithmic  | The user's algorithmic consent, it tells to the algorithm what are the allowed actions in order to use personal data                                                                                                               |
| source                | The source to which the profile belongs                                                                                                                                                                                            |
| updated\_at           | Time at which the object was last updated                                                                                                                                                                                          |
| created\_at           | Time at which the object was created                                                                                                                                                                                               |
| info                  | The Profile's [Info](https://developers.hrflow.ai/hr-json/profile-objects/info-object) object, it contains all personal information such as first/last name email, phone                                                           |
| text                  | The Profile's text, it contains a long resume of a profile, it is generated based on parsed text                                                                                                                                   |
| text\_language        | The original language of the document                                                                                                                                                                                              |
| educations            | A list of [Educations](https://developers.hrflow.ai/hr-json/profile-objects/education-object) object, education is identified by a unique key                                                                                      |
| educations\_duration  | Education's duration                                                                                                                                                                                                               |
| experiences           | A list of [Experiences](https://developers.hrflow.ai/hr-json/profile-objects/experience-object) object, experience is identified by a unique key                                                                                   |
| experiences\_duration | Experience's duration, it calculates the profile's seniority                                                                                                                                                                       |
| attachments           | A list of profile's [Attachments](https://developers.hrflow.ai/hr-json/profile-objects/attachment-object) object                                                                                                                   |
| certifications        | A list of profile's [Certifications](https://developers.hrflow.ai/hr-json/trait-objects/certification-object) object                                                                                                               |
| courses               | A list of profile's [Courses](https://developers.hrflow.ai/hr-json/trait-objects/course-object) object                                                                                                                             |
| tasks                 | A list of profile's [Tasks](https://developers.hrflow.ai/hr-json/trait-objects/task-object) object                                                                                                                                 |
| skills                | A list of profile's [Skills](https://developers.hrflow.ai/hr-json/trait-objects/skill-object) object                                                                                                                               |
| languages             | A list of profile's [Languagse](https://developers.hrflow.ai/hr-json/trait-objects/language-object) object                                                                                                                         |
| interests             | A list of profile's [Interests](https://developers.hrflow.ai/hr-json/trait-objects/interest-object) object                                                                                                                         |
| labels                | A list of [Labels](https://developers.hrflow.ai/hr-json/profile-objects/label-object) object that you can attach to an object                                                                                                      |
| tags                  | A list of [Tags](https://developers.hrflow.ai/hr-json/trait-objects/tag-object) object that you can include with an object. This can be helpful in attaching tags to a profile                                                     |
| metadatas             | A list of [Metadata](https://developers.hrflow.ai/hr-json/trait-objects/metadata-object) object that you can include with an object. This can be useful for storing additional information about the object in a structured format |
