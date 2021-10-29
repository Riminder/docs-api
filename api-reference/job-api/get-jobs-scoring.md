---
description: This endpoint allows you to get job's scoring.
---

# GET: /jobs/scoring

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/jobs/scoring" method="get" summary="Get /jobs/scoring" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="names" type="array" %}
List of job' s title to include in the query
{% endswagger-parameter %}

{% swagger-parameter in="query" name="source_key" type="string" %}
The source's unique identifier containing the given Profile.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="profile_key" type="string" %}
The Profile unique identifier
{% endswagger-parameter %}

{% swagger-parameter in="query" name="board_keys" type="array" %}
Only Jobs in these boards will be scored
{% endswagger-parameter %}

{% swagger-parameter in="query" name="agent_key" type="string" %}
The agent unique identifier
{% endswagger-parameter %}

{% swagger-parameter in="query" name="use_agent" type="integer" %}
In order to enable scoring engine you set this parameter to 1 otherwise it enables only searching engine
{% endswagger-parameter %}

{% swagger-parameter in="query" name="limit" type="integer" %}
Total job to score, default value is 30
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="integer" %}
API page offset, default value is 30
{% endswagger-parameter %}

{% swagger-parameter in="query" name="order_by" type="string" %}
Order by (ie. desc or asc)

\


Default is "desc"
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sort_by" type="string" %}
Sort by (ie. created_at)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="date_range_min" type="string" %}
Minimum creation datetime in iso format
{% endswagger-parameter %}

{% swagger-parameter in="query" name="date_range_max" type="string" %}
Maximum creation datetime in iso format
{% endswagger-parameter %}

{% swagger-parameter in="query" name="location_geopoint" type="object" %}
Filter by location's latitude and longitude

\


(ie. {"lat":35.7516600, "lng":10.7110900})
{% endswagger-parameter %}

{% swagger-parameter in="query" name="location_distance" type="integer" %}
If location's latitude and longitude are present, you can set radius in filter query
{% endswagger-parameter %}

{% swagger-parameter in="query" name="summary_keywords" type="array" %}
Filter by keywords in summary
{% endswagger-parameter %}

{% swagger-parameter in="query" name="text_keywords" type="array" %}
Filter by keywords in text
{% endswagger-parameter %}

{% swagger-parameter in="query" name="skills" type="array" %}
Filter by skills
{% endswagger-parameter %}

{% swagger-parameter in="query" name="languages" type="array" %}
Filter by languages
{% endswagger-parameter %}

{% swagger-parameter in="query" name="tags_included" type="array" %}
Filter by tags to include
{% endswagger-parameter %}

{% swagger-parameter in="query" name="tags_excluded" type="array" %}
Filter by tags to exclude
{% endswagger-parameter %}

{% swagger-parameter in="query" name="ranges_float" type="array" %}
Filter by range floats
{% endswagger-parameter %}

{% swagger-parameter in="query" name="ranges_date" type="array" %}
Filter by range dates
{% endswagger-parameter %}

{% swagger-response status="200" description="Jobs successfully retrieved" %}
```python
{
    "code": 200,
    "message": "Job scoring results",
    "meta": {
        "page": 1,
        "maxPage": 73,
        "count": 1,
        "total": 73
    },
    "data": {
        "jobs": [
            {...}
        ],
        "predictions": [
            [
                0.031190164387226105,
                0.96880990266799927
            ]
        ]
    }
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Invalid secret key" %}
```python
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

client.job.scoring.list(board_keys=["board_key1", "board_key2"],
                          source_key="source_key", profile_key="profile_key", 
                          agent_key="agent_key", use_agent=1,
                          name="data scientist", page=1, limit=10, 
                          order_by="asc", sort_by="created_at",
                          text_keywords=["engineer", "python"],
                          tags_included=[[{"name": "active", "value": True}]],
                          location_distance=30,
                          location_geopoint={"lat":33.59662,"lng":-7.61889})
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';
const client = new Hrflow({ 
    api_secret: "Your API Key",
    api_user: "Your API user email" 
});

client.job.scoring.list(["board_key1", "board_key2"], "agent_key",
    "source_key", "profile_key", {
        name: "data scientist",
        page: 1,
        limit: 10,
        order_by: "asc",
        sort_by: "date",
        text_keywords: ["engineer", "python"],
        tags_included: [[{name: "active", value: true}]],
        location_distance: 30,
        location_geopoint: {"lat":33.59662,"lng":-7.61889}
    }
);
```
{% endtab %}
{% endtabs %}
