---
description: This endpoint allows you to search profiles based on filters.
---

# GET: /profiles/searching

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/profiles/searching" method="get" summary="Get /profiles/searching" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="source_keys" type="array" %}
Only Profiles in these sources will be scored
{% endswagger-parameter %}

{% swagger-parameter in="query" name="stage" type="string" %}
Filter by Profile's stage (ie. 'new', 'yes', 'later', 'no'), default value is 'new'
{% endswagger-parameter %}

{% swagger-parameter in="query" name="limit" type="integer" %}
Total profiles to score, default value is 30
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="integer" %}
API page offset, default value is 1
{% endswagger-parameter %}

{% swagger-parameter in="query" name="order_by" type="string" %}
Order by (ie. asc, desc), default value is "desc"
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sort_by" type="string" %}
Sort by (ie. created_at, updated_at, location, location_experience, location_education, searching, scoring )
{% endswagger-parameter %}

{% swagger-parameter in="query" name="created_at_min" type="string" %}
Filter by minimum creation date
{% endswagger-parameter %}

{% swagger-parameter in="query" name="created_at_max" type="string" %}
Filter by maximum creation date
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" %}
Filter by Profile's name
{% endswagger-parameter %}

{% swagger-parameter in="query" name="email" type="string" %}
Filter by Profile's email
{% endswagger-parameter %}

{% swagger-parameter in="query" name="location_geopoint" type="object" %}
Filter by location's latitude and longitude

\


(ie. {"lat":35.7516600, "lng":10.7110900} )
{% endswagger-parameter %}

{% swagger-parameter in="query" name="location_distance" type="integer" %}
If location's latitude and longitude are present, you can set radius in filter query
{% endswagger-parameter %}

{% swagger-parameter in="query" name="summary_keywords" type="array" %}
Filter by keywords that can exist in a summary
{% endswagger-parameter %}

{% swagger-parameter in="query" name="text_keywords" type="array" %}
Filter by text keywords
{% endswagger-parameter %}

{% swagger-parameter in="query" name="experience_keywords" type="array" %}
Filter by experience keywords
{% endswagger-parameter %}

{% swagger-parameter in="query" name="experience_location_geopoint" type="object" %}
Filter by experience location's latitude and longitude
{% endswagger-parameter %}

{% swagger-parameter in="query" name="experience_location_distance" type="integer" %}
Set experience's location radius
{% endswagger-parameter %}

{% swagger-parameter in="query" name="experiences_duration_min" type="integer" %}
Filter by minimum seniority
{% endswagger-parameter %}

{% swagger-parameter in="query" name="experiences_duration_max" type="integer" %}
Filter by maximum seniority
{% endswagger-parameter %}

{% swagger-parameter in="query" name="education_keywords" type="array" %}
Filter by education keywords
{% endswagger-parameter %}

{% swagger-parameter in="query" name="education_location_geopoint" type="object" %}
Filter by education's latitude and longitude
{% endswagger-parameter %}

{% swagger-parameter in="query" name="education_location_distance" type="integer" %}
Set education's location radius
{% endswagger-parameter %}

{% swagger-parameter in="query" name="educations_duration_min" type="integer" %}
Filter by minimum education duration
{% endswagger-parameter %}

{% swagger-parameter in="query" name="educations_duration_max" type="integer" %}
Filter by education maximum duration
{% endswagger-parameter %}

{% swagger-parameter in="query" name="skills" type="array" %}
Filter by a list of skills

\


( ie. [{ name: 'python', value: 0.9 }] )
{% endswagger-parameter %}

{% swagger-parameter in="query" name="languages" type="array" %}
Filter by a list of languages

\


( ie. [{ name: 'english', value: 'fluent' }] )
{% endswagger-parameter %}

{% swagger-parameter in="query" name="interests" type="array" %}
Filter by a list of interests

\


(ie. [{ name: 'football', value: null }] )
{% endswagger-parameter %}

{% swagger-parameter in="query" name="tags_included" type="array" %}
Filter by a List of tags to include (ie. [{ name: 'active', value: true }] )
{% endswagger-parameter %}

{% swagger-parameter in="query" name="tags_excluded" type="array" %}
Filter by a List of tags to exclude (ie. [{ name: 'active', value: false }] )
{% endswagger-parameter %}

{% swagger-response status="200" description="Profiles successfully retrieved." %}
```scheme
{
    "code": 200,
    "message": "Profiles list",
    "page": 1,
    "max_page": 1,
    "count": 3,
    "total": 3,
    "data": {
        "profiles": [
            {
                "date_creation": "2019-01-15T12:09:58",
                "date_reception": "2019-01-15T12:09:42",
                "educations": [
                    {
                        "description": "Hogwarts School of Witchcraft and Wizardry",
                        "end_date": {...},
                        "id": "education_id",
                        "location": {...}
                        },
                        "school": "Hogwarts",
                        "start_date": {...},
                        "title": "MASTER IN APPLIED MATHEMATICS AND SIGNAL PROCESSING"
                    },
                    .
                    .
                    .
                    ],
                "educations_duration": n,
                "email": {
                    "text": "harry.potter@gmail.com"
                },
                "experiences": [
                    {
                        "company": "Gryffindor",
                        "description": "Chemistry – Potioneer.",
                        "end_date": {....},
                        "id": "experience_id",
                        "location": {...},
                        },
                        "start_date": {...},
                        "title": "Machine Learning Engineer"
                    },
                    .
                    .
                    .

                ],
                "experiences_duration": 1.2547945205479452,
                "interests": [{"name": "Psychology","value": null}],
                "labels": [{
                        "date_rating": "2019-07-15T14:51:07",
                        "date_stage": "2019-07-15T14:51:07",
                        "job_id": "job_id",
                        "job_reference": "19051996",
                        "rating": null,
                        "stage": "yes"
                    }],
                "languages": [
                    {"name": "english","value": null},
                    {"name": "french","value": null}
                ],
                "location": {...},
                "name": {
                    "first_name": "Harry",
                    "last_name": "Potter",
                    "text": "Harry Potter"
                },
                "profile_id": "profile_id",
                "skills": [
                    {
                        "is_predicted": false,
                        "name": "Chemistry",
                        "type": "hard_skill",
                        "value": null
                    },
                ],
                "source_id": "source_id",
                "summary": "Bayesian Optimization",
                "team_id": "team_id",
                "text": {...},
                "urls": {
                    "facebook": null,
                    "from_resume": [],
                    "github": null,
                    "linkedin": null,
                    "picture": null,
                    "twitter": null
                },
                "uuid": "uuid"
            }
        ],
        "predictions": []
    }
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Could not find a source matching this query." %}
```scheme
{
    "code": 400,
    "message": "Bad Request. Invalid source ids"
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Invalid secret key." %}
```scheme
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxxx "
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Python" %}
```python
from hrflow import Hrflow

client = Hrflow(api_secret="Your API Key", api_user="Your API user email")

client.profile.searching.list(source_keys=["source_key1", "source_key2"],
                            limit=10, page=1, order_by='asc',
                            sort_by='created_at', created_at_min='2020-05-15T23:59:59.999Z',
                            created_at_max='2020-07-15T23:59:59.999Z', name='name',
                            email='exemple@exemple.com',
                            location_geopoint={
                              'lat':'357516600',
                              'lon':'10.7110900',
                            },
                            location_distance=40,
                            summary_keywords=["keyword1", "keyword2"],
                            text_keywords=["keyword1", "keyword2"],
                            experience_keywords=["keyword1", "keyword2"],
                            experience_location_geopoint={
                              'lat': 35.7516600,
                              'lon': 10.7110900,
                            },
                            experience_location_distance=40,
                            experiences_duration_min=3,
                            experiences_duration_max=7,
                            skills=[{"name": "python", "value": 0.9}],
                            languages=[{"name": "english", "value": "fluent"}],
                            interests=[{"name": "design", "value": 1}],
                            tags_included=[{"name": "active", "value":True}]
                            )
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';
const client = new Hrflow({ 
    api_secret: "Your API Key",
    api_user: "Your API user email" 
});

client.profile.searching.list(['source_key1', 'source_key2'], {
  stage: 'new,
  limit: 10,
  page: 1,
  order_by: 'asc',
  sort_by: 'created_at',
  created_at_min: '2020-05-15T23:59:59.999Z',
  created_at_max: '2020-07-15T23:59:59.999Z',
  name: 'name',
  email: 'exemple@exemple.com',
  location_geopoint: {
    lat: '357516600',
    lon: '10.7110900',
  },
  location_distance: 40,
  summary_keywords: ['keyword1', 'keyword2'],
  text_keywords: ['keyword1', 'keyword2'],
  experience_keywords: ['keyword1', 'keyword2'],
  experience_location_geopoint: {
    lat: '357516600',
    lon: '10.7110900',
  },
  experience_location_distance:  40,
  experiences_duration_min: 3,
  experiences_duration_max: 7,
  skills: [{name: 'python', value: 0.9}],
  languages: [{name: 'english', value: 'fluent'}],
  interests: [{name: 'design', value: 1}],
  tags: [{name: 'active', value: true}],
});
```
{% endtab %}
{% endtabs %}
