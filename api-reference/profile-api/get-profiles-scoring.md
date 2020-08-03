---
description: Retrieve profile's scoring given profile id and source_id.
---

# \[GET\] /profiles/scoring

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/profiles/scoring" %}
{% api-method-summary %}
/profiles/scoring
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to score list of profiles for a given job.
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
{% api-method-parameter name="source\_keys" type="array" required=true %}
List of source keys
{% endapi-method-parameter %}

{% api-method-parameter name="use\_agent" type="array" required=false %}
Use agent or not \(ie. 0 or 1\)
{% endapi-method-parameter %}

{% api-method-parameter name="board\_key" type="integer" required=false %}
Board key
{% endapi-method-parameter %}

{% api-method-parameter name="job\_key" type="string" required=true %}
Job key
{% endapi-method-parameter %}

{% api-method-parameter name="stage" type="string" required=false %}
Stage \(ie. 'new', 'yes', 'later', 'no'\)
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
Total profiles to score
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="integer" required=false %}
API page offset
{% endapi-method-parameter %}

{% api-method-parameter name="order\_by" type="string" required=false %}
order by \(ie. asc, desc\)
{% endapi-method-parameter %}

{% api-method-parameter name="sort\_by" type="string" required=false %}
sort by \(ie. reception date, location, location\_experience,  
location\_education, semantic score, predictive score\)
{% endapi-method-parameter %}

{% api-method-parameter name="timestamp\_start" type="integer" required=false %}
start date
{% endapi-method-parameter %}

{% api-method-parameter name="timestamp\_end" type="integer" required=false %}
end date
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
Profile's name
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=false %}
Profile"s email
{% endapi-method-parameter %}

{% api-method-parameter name="location\_geopoint" type="object" required=false %}
Filter by location's latitude and longitude   
\(ie. {"lat":35.7516600, "lng":10.7110900}\)
{% endapi-method-parameter %}

{% api-method-parameter name="location\_distance" type="integer" required=false %}
max radius
{% endapi-method-parameter %}

{% api-method-parameter name="summary\_keywords" type="object" required=false %}
Filter by keywords in a summary
{% endapi-method-parameter %}

{% api-method-parameter name="text\_keywords" type="string" required=false %}
Filter by keyword in a text
{% endapi-method-parameter %}

{% api-method-parameter name="experience\_keywords" type="string" required=false %}
Filter by experience keywords
{% endapi-method-parameter %}

{% api-method-parameter name="experience\_location\_geopoint" type="string" required=false %}
Filter by experience location's latitude and longitude
{% endapi-method-parameter %}

{% api-method-parameter name="experiences\_duration\_min" type="string" required=false %}
Filter by experience duration min
{% endapi-method-parameter %}

{% api-method-parameter name="experiences\_duration\_max" type="string" required=false %}
Filter by experience duration max
{% endapi-method-parameter %}

{% api-method-parameter name="education\_keywords" type="string" required=false %}
Filter by education keywords
{% endapi-method-parameter %}

{% api-method-parameter name="education\_location\_geopoint" type="string" required=false %}
Filter by education's latitude and longitude
{% endapi-method-parameter %}

{% api-method-parameter name="education\_location\_distance" type="string" required=false %}
Filter by education's location raduis 
{% endapi-method-parameter %}

{% api-method-parameter name="educations\_duration\_min" type="string" required=false %}
Filter by education duration min
{% endapi-method-parameter %}

{% api-method-parameter name="educations\_duration\_max" type="string" required=false %}
Filter by education duration max
{% endapi-method-parameter %}

{% api-method-parameter name="skills\_dict" type="object" required=false %}
Filter by skills.
{% endapi-method-parameter %}

{% api-method-parameter name="languages\_dict" type="object" required=false %}
Filter by languages.
{% endapi-method-parameter %}

{% api-method-parameter name="tags\_dict" type="object" required=false %}
Filter by tags
{% endapi-method-parameter %}

{% api-method-parameter name="interests\_dict" type="object" required=false %}
Filter by interests
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Profiles are successfully scored
{% endapi-method-response-example-description %}

```scheme
{
    "code": 200,
    "message": "Profiles list",
    "page": 1,
    "max_page": 1,
    "count": 1,
    "total": 1,
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
        "predictions": [
            [
                0.49184858798980713,
                0.50815147161483765
            ]
        ]
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

### Example

{% tabs %}
{% tab title="PHP" %}
```php
$client = new Hrflow\Client('your secret key');

$params = [
  'use_agent'         => 1,
  'stage'             => 'yes',
  'limit'             => 10,
  'page'              => 1,
  'order_by'          => 'asc',
  'sort_by'           => 'date_reception',
  'timestamp_start'   => 1569320033,
  'timestamp_end'     => 1586945633,
  'name'              => 'name',
  'email'             => 'exemple@exemple.com',
  'location_geopoint' => [
    'lat' => '357516600',
    'lng' => '10.7110900',
  ],
  'location_distance'            => 40,
  'summary_keywords'             => ['keyword1', 'keyword2',...],
  'text_keywords'                => ['keyword1', 'keyword2',...],
  'experience_keywords'          => ['keyword1', 'keyword2',...],
  'experience_location_geopoint' => [
    'lat' => '357516600',
    'lng' => '10.7110900',
  ],
  'experience_location_distance' => 40,
  'experiences_duration_min'     => 3,
  'experiences_duration_max'     => 7,
  'skills_dict'                  => ['skill1', 'skill2', ...],
  'languages_dict'               => ['lang1',..],
  'interests_dict'               => ['interest1', 'interest2',...],
  'tags_dict'                    => ['tag1', 'tag2', ...],
]

$client->profile->searching->get($source_ids, $job_id, $params);
```
{% endtab %}

{% tab title="Python" %}
```python
import hrflow as hf

client = hf.client(api_secret='your secret key')

client.profile.searching.get(source_ids=["source_id"], job_id, stage, 
                             use_agent,
                             name=None, email=None,
                             location_geopoint=[], location_distance=None, 
                             summary_keywords=[], text_keywords=[],
                             experience_keywords=[],
                             experience_location_geopoint=[], 
                             experience_location_distance=None, 
                             experiences_duration_min=None, 
                             experiences_duration_max=None,
                             education_keywords=[], 
                             education_location_geopoint=[], 
                             education_location_distance=None,
                             educations_duration_min=None, 
                             educations_duration_max=None,
                             skills_dict=[], languages_dict=[], 
                             interests_dict=None, labels_dict=None,
                             date_start="1494539999", date_end=None, 
                             page=1, limit=30, sort_by='date_reception', 
                             order_by='asc')
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
// npm install --save hrflow

import Hrflow from 'hrflow';
const client = new Hrflow({API_Key: "Your API Key"});

const params = {
  source_ids: ['source_id1', 'source_id2',..], // Required, list of sources ids
  job_id: 'job_id', // Required, job id
  use_agent: 1, // Use agent or not (ie. 0 or 1)
  stage: 'yes', // stage (ie. 'new', 'yes', 'later', 'no')
  limit: 10, //  Total profiles to search
  page: 1, //  Page number
  order_by: 'asc', // Order by 'asc' or 'desc'
  sort_by: 'date_reception', // Sort by 'date_reception', 'date_creation', 'location', 'location_experience', 'location_education', 'score_semantic'  or 'score_predictive'
  timestamp_start: 1569320033, // 'Start date'
  timestamp_end: 1586945633,  // 'Start date'
  name: 'name', // Profile's name  
  email: 'exemple@exemple.com', // Profile's email
  location_geopoint: {
    // Filter by location's latitude and longitude
    lat: '357516600',
    lng: '10.7110900',
  },
  location_distance: 40, // Filter by location distance in km
  summary_keywords: ['keyword1', 'keyword2',...], // Filter by summary keywords
  text_keywords: ['keyword1', 'keyword2',...], // Filter by text keywords,
  experience_keywords: ['keyword1', 'keyword2',...], // Filter by experience keywords
  experience_location_geopoint: {
  // Filter by experience's latitude and longitude
    lat: '357516600',
    lng: '10.7110900',
  },
  experience_location_distance:  40, // Filter by experience location distance in km
  experiences_duration_min: 3, // Min total years of experience
  experiences_duration_max: 7, // Max total years of experience
  skills_dict: ['skill1', 'skill2', ...], // List of skills
  languages_dict: ['lang1',..], // List of language
  interests_dict: ['interest1', 'interest2',...], // List of interests 
  tags_dict: ['tag1', 'tag2', ...], // List of tags
}

hrflow.profile.scoring.list(params);
```
{% endtab %}
{% endtabs %}

