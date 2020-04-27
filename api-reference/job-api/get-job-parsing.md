---
description: Retrieve job's parsing given job id or job reference.
---

# \[GET\] /job/parsing

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/job/parsing" %}
{% api-method-summary %}
Get /job/parsing
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to job's parsing.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="job\_id" type="string" required=true %}
Job id
{% endapi-method-parameter %}

{% api-method-parameter name="job\_reference" type="string" required=false %}
Job reference
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 200,
    "message": "Profile parsing",
    "data": {
        "job_id": "job_id",
        "job_reference": "19051996",
        "name": "Data Scientist",
        "description": null,
        "query": {
            "skills": [
                "data",
                "python"
            ],
            "experiences_duration_min": 2,
            "experiences_duration_max": 9,
            "educations_duration_min": 3,
            "educations_duration_max": 100000000000,
            "is_geo_loc": false,
            "is_exp_geo_loc": true,
            "is_edu_geo_loc": false,
            "location_lat": 33.971590399999997,
            "location_lng": -6.8498128999999999,
            "radius": 34000
        },
        "agent": [],
        "notification": false,
        "archive": false,
        "date_creation": {
            "date": "2018-08-01 10:19:37.000000",
            "timezone_type": 3,
            "timezone": "UTC"
        }
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a job matching this query.
{% endapi-method-response-example-description %}

```
{
    "code": 400,
    "message": "Bad request. Invalid job info:xxxx"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret key.
{% endapi-method-response-example-description %}

```
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxxx "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



