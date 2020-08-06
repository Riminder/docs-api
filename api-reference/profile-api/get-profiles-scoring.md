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
{% api-method-parameter name="board\_key" type="string" required=true %}
Board key
{% endapi-method-parameter %}

{% api-method-parameter name="job\_key" type="string" required=true %}
Job key
{% endapi-method-parameter %}

{% api-method-parameter name="source\_keys" type="array" required=true %}
List of source keys
{% endapi-method-parameter %}

{% api-method-parameter name="use\_agent" type="array" required=false %}
Use agent or not \(ie. 0 or 1\)  
default is 1
{% endapi-method-parameter %}

{% api-method-parameter name="stage" type="string" required=false %}
Stage \(ie. 'new', 'yes', 'later', 'no'\)  
Default is 'new'
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
Total profiles to score  
Default is 12
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="integer" required=false %}
API page offset  
Default is 1
{% endapi-method-parameter %}

{% api-method-parameter name="order\_by" type="string" required=false %}
order by \(ie. asc, desc\)  
Default is "desc"
{% endapi-method-parameter %}

{% api-method-parameter name="sort\_by" type="string" required=false %}
sort by \(ie. scoring, searching, date\)  
Default is "date"
{% endapi-method-parameter %}

{% api-method-parameter name="created\_at\_min" type="string" required=false %}
start date as  iso string date
{% endapi-method-parameter %}

{% api-method-parameter name="created\_at\_max" type="string" required=false %}
end date as iso string date 
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
Profile's name
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=false %}
Profile"s email
{% endapi-method-parameter %}

{% api-method-parameter name="location\_geopoint" type="object" required=false %}
Location's latitude and longitude   
\(ie. {"lat":35.7516600, "lng":10.7110900} \)
{% endapi-method-parameter %}

{% api-method-parameter name="location\_distance" type="integer" required=false %}
Max radius
{% endapi-method-parameter %}

{% api-method-parameter name="summary\_keywords" type="array" required=false %}
Keywords in a summary
{% endapi-method-parameter %}

{% api-method-parameter name="text\_keywords" type="array" required=false %}
Keyword in a text
{% endapi-method-parameter %}

{% api-method-parameter name="experience\_keywords" type="array" required=false %}
Experience keywords
{% endapi-method-parameter %}

{% api-method-parameter name="experience\_location\_geopoint" type="object" required=false %}
Experience location's latitude and longitude
{% endapi-method-parameter %}

{% api-method-parameter name="experiences\_duration\_min" type="integer" required=false %}
Experience duration min
{% endapi-method-parameter %}

{% api-method-parameter name="experiences\_duration\_max" type="integer" required=false %}
Experience duration max
{% endapi-method-parameter %}

{% api-method-parameter name="education\_keywords" type="array" required=false %}
Education keywords
{% endapi-method-parameter %}

{% api-method-parameter name="education\_location\_geopoint" type="object" required=false %}
Education's latitude and longitude
{% endapi-method-parameter %}

{% api-method-parameter name="education\_location\_distance" type="number" required=false %}
Education's location raduis 
{% endapi-method-parameter %}

{% api-method-parameter name="educations\_duration\_min" type="number" required=false %}
Education duration min
{% endapi-method-parameter %}

{% api-method-parameter name="educations\_duration\_max" type="number" required=false %}
Education duration max
{% endapi-method-parameter %}

{% api-method-parameter name="skills" type="array" required=false %}
List of skills \( ie. \[{ name: 'python', value: 0.9 }\] \)
{% endapi-method-parameter %}

{% api-method-parameter name="languages" type="array" required=false %}
List of languages \( ie. \[{ name: 'english', value: 'fluent' }\] \) 
{% endapi-method-parameter %}

{% api-method-parameter name="tags" type="array" required=false %}
List of tags \(ie. \[{ name: 'active', value: true }\] \)
{% endapi-method-parameter %}

{% api-method-parameter name="interests" type="array" required=false %}
List of interests \(ie. \[{ name: 'football', value: null }\] \)
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

client = hf.client(api_secret="Your API Key", api_user="Your API user email")

client.profile.scoring.list(source_keys=["source_key1", "source_key2"],
                            board_key="board_key", job_key="job_key", use_agent= 1,
                            stage="new", limit: 10, page: 1, order_by: 'asc',
                            sort_by='date', created_at_min='2020-05-15T23:59:59.999Z',
                            created_at_max='2020-07-15T23:59:59.999Z', name='name',
                            email='exemple@exemple.com',
                            location_geopoint={
                              lat:'357516600',
                              lon:'10.7110900',
                            },
                            location_distance=40,
                            summary_keywords=["keyword1", "keyword2"],
                            text_keywords=["keyword1", "keyword2"],
                            experience_keywords=["keyword1", "keyword2"],
                            experience_location_geopoint={
                              lat: 35.7516600,
                              lon: 10.7110900',
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

client.profile.scoring.list(['source_key1', 'source_key2'], "board_key", 
  "job_key", {
  use_agent: 1,
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

