---
description: Retrieve a list of profiles based on given filters
---

# \[GET\] /profiles/searching

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/profiles/searching" %}
{% api-method-summary %}
Get /profiles/searching
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to search profiles based on filters.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token.
{% endapi-method-parameter %}

{% api-method-parameter name="X-USER-EMAIL" type="string" required=true %}
User's email.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="source\_keys" type="string" required=true %}
List of source key
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
Total profiles to search per page
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="integer" required=false %}
API page offset
{% endapi-method-parameter %}

{% api-method-parameter name="order\_by" type="string" required=false %}
order by \(ie. asc, desc\)
{% endapi-method-parameter %}

{% api-method-parameter name="sort\_by" type="string" required=false %}
sort by \(ie. scoring, searching, date \)
{% endapi-method-parameter %}

{% api-method-parameter name="created\_at\_min" type="string" required=false %}
Start date as iso string date
{% endapi-method-parameter %}

{% api-method-parameter name="created\_at\_max" type="string" required=false %}
End date as iso string date
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
Profile's name
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=false %}
Profile's email
{% endapi-method-parameter %}

{% api-method-parameter name="location\_geopoint" type="object" required=false %}
Filter by location's latitude and longitude  
\(ie. {"lat":35.7516600, "lng":10.7110900}\)
{% endapi-method-parameter %}

{% api-method-parameter name="location\_distance" type="number" required=false %}
Filter by raduis
{% endapi-method-parameter %}

{% api-method-parameter name="summary\_keywords" type="array" required=false %}
Keywords in a summary
{% endapi-method-parameter %}

{% api-method-parameter name="text\_keywords" type="array" required=false %}
Keywords in a summary
{% endapi-method-parameter %}

{% api-method-parameter name="experience\_keywords" type="array" required=false %}
Filter by experience keywords
{% endapi-method-parameter %}

{% api-method-parameter name="experience\_location\_geopoint" type="array" required=false %}
Filter by experience location's latitude and longitude
{% endapi-method-parameter %}

{% api-method-parameter name="experience\_location\_distance" type="array" required=false %}
Filter by experience location radius
{% endapi-method-parameter %}

{% api-method-parameter name="experiences\_duration\_min" type="number" required=false %}
Filter by experience duration min
{% endapi-method-parameter %}

{% api-method-parameter name="experiences\_duration\_max" type="number" required=false %}
Filter by experience duration max
{% endapi-method-parameter %}

{% api-method-parameter name="education\_keywords" type="array" required=false %}
Filter by education keywords
{% endapi-method-parameter %}

{% api-method-parameter name="education\_location\_geopoint" type="object" required=false %}
Filter by education location's latitude and longitude
{% endapi-method-parameter %}

{% api-method-parameter name="education\_location\_distance" type="number" required=false %}
Filter by education location radius
{% endapi-method-parameter %}

{% api-method-parameter name="educations\_duration\_min" type="number" required=false %}
Filter by education duration min
{% endapi-method-parameter %}

{% api-method-parameter name="educations\_duration\_max" type="number" required=false %}
Filter by education duration max
{% endapi-method-parameter %}

{% api-method-parameter name="skills" type="array" required=false %}
List of skills \( ie. \[{ name: 'python', value: 0.9 }\] \)
{% endapi-method-parameter %}

{% api-method-parameter name="languages" type="array" required=false %}
List of languages \( ie. \[{ name: 'english', value: 'fluent' }\] \)
{% endapi-method-parameter %}

{% api-method-parameter name="interests" type="array" required=false %}
 List of interests \( ie. \[{ name: 'football', value: null }\]  
{% endapi-method-parameter %}

{% api-method-parameter name="tags" type="array" required=false %}
List of tags \(ie. \[{ name: 'active', value: true }\] \)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Profiles successfully retrieved.
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a source matching this query.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 400,
    "message": "Bad Request. Invalid source ids"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret key.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxxx "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
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
  sort_by: 'date',
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

