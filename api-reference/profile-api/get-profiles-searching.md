---
description: Retrieve a list of profiles based on given filters
---

# GET /profiles/searching

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/profile/searching" %}
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
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="source\_ids" type="string" required=true %}
List of source id
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
Total profiles to search
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
Profile's email
{% endapi-method-parameter %}

{% api-method-parameter name="location\_geopoint" type="object" required=false %}
Filter by location's latitude and longitude  
\(ie. {"lat":357516600, "lon":10.7110900}\)
{% endapi-method-parameter %}

{% api-method-parameter name="location\_distance" type="integer" required=false %}
Filter by raduis
{% endapi-method-parameter %}

{% api-method-parameter name="summary\_keywords" type="string" required=false %}
Filter by summary keywords
{% endapi-method-parameter %}

{% api-method-parameter name="text\_keywords" type="array" required=false %}
Filter by text keyword
{% endapi-method-parameter %}

{% api-method-parameter name="experience\_keywords" type="array" required=false %}
Filter by experience keywords
{% endapi-method-parameter %}

{% api-method-parameter name="experience\_location\_geopoint" type="object" required=false %}
Filter by experience location's latitude and longitude
{% endapi-method-parameter %}

{% api-method-parameter name="experience\_location\_distance" type="integer" required=false %}
Filter by experience location radius
{% endapi-method-parameter %}

{% api-method-parameter name="experiences\_duration\_min" type="integer" required=false %}
Filter by experience duration min
{% endapi-method-parameter %}

{% api-method-parameter name="experiences\_duration\_max" type="integer" required=false %}
Filter by experience duration max
{% endapi-method-parameter %}

{% api-method-parameter name="education\_keywords" type="array" required=false %}
Filter by education keywords
{% endapi-method-parameter %}

{% api-method-parameter name="education\_location\_geopoint" type="object" required=false %}
Filter by education location's latitude and longitude
{% endapi-method-parameter %}

{% api-method-parameter name="education\_location\_distance" type="integer" required=false %}
Filter by education location radius
{% endapi-method-parameter %}

{% api-method-parameter name="educations\_duration\_min" type="integer" required=false %}
Filter by education duration min
{% endapi-method-parameter %}

{% api-method-parameter name="educations\_duration\_max" type="integer" required=false %}
Filter by education duration max
{% endapi-method-parameter %}

{% api-method-parameter name="skills\_dict" type="array" required=false %}
Filter by skills
{% endapi-method-parameter %}

{% api-method-parameter name="languages\_dict" type="array" required=false %}
Filter by languages
{% endapi-method-parameter %}

{% api-method-parameter name="interests\_dict" type="array" required=false %}
Filter by interests
{% endapi-method-parameter %}

{% api-method-parameter name="tags\_dict" type="array" required=false %}
Filter by tags
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


