---
description: Add job
---

# POST /job

{% hint style="info" %}
This endpoint requires at least name, agent\_id and job\_reference.
{% endhint %}

Job post accepts json files.

Please find below an example of json job.

```javascript
{
    "title": "Data miner",
    "description": "This job is made for you",
    "contract": "CDI",
    "company": "hrflow",
    "location": "San francisco, USA",
    "profiles": {"Data Scientist", "Data Engineer", "Data miner"},
    "skills": {"Math", "Python", "Deep learning"},
    "experiences_duration": 3,
    "educations_duration": 10,
    "salary": "100K"
}
```

You can include complementary information such as :

* job's labels,
* job's tags,
* job's metadata.

Finally here an example of json to post

```javascript
{
    "name":"title", 
    "agent_id":"bdc82215e5eeeaa40608b3d9e2e3b59398811c64",
    "job_reference" : "reference_4",
    "job_labels" : "job_labels",
    "job_tags" : "job_tags",
    "job_metadatas" : "job_metadatas",
    "timestamp_reception" : "timestamp_reception",
    "job_json": "job_json"
} 
```

{% api-method method="post" host="https://api.hrflow.ai/v1" path="/job" %}
{% api-method-summary %}
Get /job
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to post free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="data" type="string" required=true %}
Json object.
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Job successfully added.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 201,
    "message": "Job file added",
    "data": {
        "job_id": "job_id",
        "job_reference": "job's reference",
        "name": "title",
        "description": "This job is made for you",
        "query": {
            "skills": null,
            "experiences_duration_min": -1,
            "experiences_duration_max": 100,
            "educations_duration_min": -1,
            "educations_duration_max": 100,
            "is_geo_loc": false,
            "is_exp_geo_loc": false,
            "is_edu_geo_loc": false,
            "location_lat": null,
            "location_lng": null,
            "radius": null
        },
        "agent": {
            "agent_id": "agent_id",
            "name": "test",
            "description": null,
            "timestamp": {
                "date": "2020-02-12 11:39:54.000000",
                "timezone_type": 3,
                "timezone": "UTC"
            }
        },
        "notification": false,
        "archive": false,
        "date_creation": {
            "date": "2020-03-05 13:34:39.319434",
            "timezone_type": 3,
            "timezone": "UTC"
        }
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid name
{% endapi-method-response-example-description %}

```
{
    "code": 400,
    "message": "Invalid name"
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



