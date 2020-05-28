---
description: Retrieve a list of jobs based on given filters
---

# \[GET\] /jobs/searching

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/jobs/searching" %}
{% api-method-summary %}
Get /jobs/searching
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to search jobs for given query parameters.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="board\_keys" type="string" required=false %}
List of board keys
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="string" required=false %}
Total job to retrieve
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="string" required=false %}
API page offset
{% endapi-method-parameter %}

{% api-method-parameter name="order\_by" type="string" required=false %}
Order by \(ie. desc, asc\)
{% endapi-method-parameter %}

{% api-method-parameter name="sort\_by" type="string" required=false %}
Sort by \(ie. created\_at\)
{% endapi-method-parameter %}

{% api-method-parameter name="date\_range\_min" type="string" required=false %}
Start date as iso format
{% endapi-method-parameter %}

{% api-method-parameter name="date\_range\_max" type="string" required=false %}
End date as iso format
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
Filter by job's name
{% endapi-method-parameter %}

{% api-method-parameter name="location\_geopoint" type="string" required=false %}
Filter by location's lattitude and longitude  
\(ie. {"lat"35.7516600: , "lon":10.7110900}\)
{% endapi-method-parameter %}

{% api-method-parameter name="location\_distance" type="string" required=false %}
Max raduis
{% endapi-method-parameter %}

{% api-method-parameter name="summary\_keywords" type="string" required=false %}
Filter by summary keywords
{% endapi-method-parameter %}

{% api-method-parameter name="text\_keywords" type="string" required=false %}
Filter by text keywords
{% endapi-method-parameter %}

{% api-method-parameter name="skills" type="string" required=false %}
Filter by skills
{% endapi-method-parameter %}

{% api-method-parameter name="languages" type="string" required=false %}
Filter by languages
{% endapi-method-parameter %}

{% api-method-parameter name="tags" type="string" required=false %}
Filter by tags
{% endapi-method-parameter %}

{% api-method-parameter name="ranges\_float" type="string" required=false %}
Filter by ranges float
{% endapi-method-parameter %}

{% api-method-parameter name="ranges\_date" type="string" required=false %}
Filter by ranges date
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Jobs successfully retrieved.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 200,
    "page": 1,
    "maxPage": 1,
    "count": 6,
    "total": 6,
    "message": "Job list",
    "data": [
        {
            "job_id": "job_id",
            "job_reference": null,
            "name": "Previsioniste economiste",
            "description": null,
            "query": {
                "skills": [
                    "data science"
                ],
                "experiences_duration_min": 8,
                "experiences_duration_max": 100000000000,
                "educations_duration_min": -100000000000,
                "educations_duration_max": 8,
                "is_geo_loc": false,
                "is_exp_geo_loc": false,
                "is_edu_geo_loc": false,
                "location_lat": 48.856614,
                "location_lng": 2.3522219,
                "radius": 10000
            },
            "agent": [],
            "notification": false,
            "archive": false,
            "date_creation": {
                "date": "2018-12-06 15:48:15.000000",
                "timezone_type": 3,
                "timezone": "UTC"
            },
            "stats": {
                "total_yes": "2",
                "total_later": "1",
                "total_no": "0"
            }
        },
        .
        .
        .
    ]
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

