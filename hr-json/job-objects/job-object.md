# Job object

## Profile

This object is a standard representation of a job, it is an abstraction of how it can be treated in a more faster and clearer way.

The API allows you to create, update and retrieve your job.

| **ENDPOINTS** |
| :--- |
| [**POST** /v1/job/indexing](https://developers.hrflow.ai/api-reference/job-api/post-job) |
| [**PUT** /v1/job/indexing](https://developers.hrflow.ai/api-reference/job-api/put-job) |
| [**GET** /v1/job/indexing](https://developers.hrflow.ai/api-reference/job-api/get-job) |

## The Profile Object

```python
{
      'id': 6654,
      'key': '258239ca46d6a3a63554ede6bf19b75a4d8dba3b',
      'reference': "Job's reference abc",
      'updated_at': '2020-07-28T14:04:33+0000',
      'created_at': '2020-07-28T14:04:33+0000',
      'name': 'Data Engineer',
      'url': 'https://www.pole-emploi.ai/jobs/data_engineer',
      'summary': 'As an engineer for the Data Engineering Infrastructure '
                 'team, you will design, build, scale, and evolve our data '
                 'engineering  platform, services and tooling. Your work '
                 'will have a critical  impact on all areas of '
                 'business:supporting detailed internal analytics, '
                 'calculating customer usage, securing our platform, and '
                 'much more.',
      'location': {'fields': [],
                   'gmaps': None,
                   'lat': None,
                   'lng': None,
                   'text': 'Dampierre en Burly (45)'},
      'sections': [{'description': 'Bac+5',
                    'name': 'profile',
                    'title': 'Searched Profile'}],
      'ranges_date': [{'name': 'Dates',
                       'value_max': '2020-09-15T21:59',
                       'value_min': '2020-05-18T21:59'}],
      'ranges_float': [{'name': 'salary',
                        'unit': 'eur',
                        'value_max': 50,
                        'value_min': 30}],
      'skills': [{'name': 'python', 'value': None},
                 {'name': 'spark', 'value': 0.9}],
      'languages': [{'name': 'english', 'value': 1},
                    {'name': 'french', 'value': 1}],
      'tags': [{'name': 'archive', 'value': True},
               {'name': 'tag example', 'value': 'tag'}],
      'metadatas': [{'name': 'metadata example', 'value': 'metadata'}]
}
```

## Attributes

| name | description |
| :--- | :--- |
| id | The document's id |
| key | Unique identifier for the object |
| reference | The Job's reference, it must be unique for a given board |
| updated\_at | Time at which the object was last updated |
| created\_at | Time at which the object was created |
| name | The Job's title |
| url | The Job's url where it is published |
| summary | The Job's summary |
| location | The Job's [Location](https://developers.hrflow.ai/hr-json/trait-objects/location-object) object |
| sections | A list of Job's [Section](https://developers.hrflow.ai/hr-json/job-objects/section-object) object, it is very usefull structured format for a section |
| ranges\_date | A list of Job's [Range Date](https://developers.hrflow.ai/hr-json/job-objects/range-date-object) object, it records all range dates that you can include with a job |
| ranges\_float | A list of Job's [Range Float](https://developers.hrflow.ai/hr-json/job-objects/range-float-object) object, it records all range floats that you can include with a job |
| skills | A list of Job's [Skill](https://developers.hrflow.ai/hr-json/trait-objects/skill-object) object |
| languages | A list of profile's [Language](https://developers.hrflow.ai/hr-json/trait-objects/language-object) object |
| tags | A list of [tag](https://developers.hrflow.ai/hr-json/trait-objects/tag-object) object that you can include with an object, This can be helpful in marking jobs |
| metadatas | A list of [metadata](https://developers.hrflow.ai/hr-json/trait-objects/metadata-object) object that you can include with an object. This can be useful for storing additional information about the object in a structured format |

