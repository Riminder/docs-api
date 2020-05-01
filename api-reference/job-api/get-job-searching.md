---
description: Retrieve a list of jobs based on given filters
---

# \[GET\] /jobs/searching

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/jobs/searching" %}
{% api-method-summary %}
Get /jobs/searching
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to search jobs for given filters.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="name" type="string" required=false %}
query string parameter
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="string" required=false %}
API page offset
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
Max job to return
{% endapi-method-parameter %}

{% api-method-parameter name="order\_by" type="integer" required=false %}
order by \(ie. asc, desc\)
{% endapi-method-parameter %}

{% api-method-parameter name="sort\_by" type="string" required=false %}
sort by \(ie. date\)
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

## Exemple

{% tabs %}
{% tab title="Javascipt" %}
```javascript
// npm install --save hrflow


import Hrflow from 'hrflow';
const client = new Hrflow({API_Key: "Your API Key"});

const params = {
    name: "data scientist",
    page: 1,
    limit: 10,
    order_by: "asc",
    sort_by: "date"
}

client.job.searching.get(params).then(response => {
    console.log(response);
});
```
{% endtab %}
{% endtabs %}

