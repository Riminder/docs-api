---
description: This endpoint allows you to get job's scoring.
---

# GET: /jobs/scoring

{% api-method method="get" host="https://api.hrflow.ai" path="/v1/jobs/scoring" %}
{% api-method-summary %}
Get /jobs/scoring
{% endapi-method-summary %}

{% api-method-description %}

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
{% api-method-parameter name="names" type="array" required=false %}
List of job' s title to include in the query
{% endapi-method-parameter %}

{% api-method-parameter name="source\_key" type="string" required=true %}
The source's unique identifier containing the given Profile.
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_key" type="string" required=true %}
The Profile unique identifier
{% endapi-method-parameter %}

{% api-method-parameter name="board\_keys" type="array" required=true %}
Only Jobs in these boards will be scored
{% endapi-method-parameter %}

{% api-method-parameter name="agent\_key" type="string" required=true %}
The agent unique identifier
{% endapi-method-parameter %}

{% api-method-parameter name="use\_agent" type="integer" required=false %}
In order to enable scoring engine you set this parameter to 1 otherwise it enables only searching engine
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
Total job to score, default value is 30
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="integer" required=false %}
API page offset, default value is 30
{% endapi-method-parameter %}

{% api-method-parameter name="order\_by" type="string" required=false %}
Order by \(ie. desc or asc\)  
Default is "desc"
{% endapi-method-parameter %}

{% api-method-parameter name="sort\_by" type="string" required=false %}
Sort by \(ie. created\_at\)
{% endapi-method-parameter %}

{% api-method-parameter name="date\_range\_min" type="string" required=false %}
Minimum creation datetime in iso format
{% endapi-method-parameter %}

{% api-method-parameter name="date\_range\_max" type="string" required=false %}
Maximum creation datetime in iso format
{% endapi-method-parameter %}

{% api-method-parameter name="location\_geopoint" type="object" required=false %}
Filter by location's latitude and longitude  
\(ie. {"lat":35.7516600, "lng":10.7110900}\)
{% endapi-method-parameter %}

{% api-method-parameter name="location\_distance" type="integer" required=false %}
If location's latitude and longitude are present, you can set radius in filter query
{% endapi-method-parameter %}

{% api-method-parameter name="summary\_keywords" type="array" required=false %}
Filter by keywords in summary
{% endapi-method-parameter %}

{% api-method-parameter name="text\_keywords" type="array" required=false %}
Filter by keywords in text
{% endapi-method-parameter %}

{% api-method-parameter name="skills" type="array" required=false %}
Filter by skills
{% endapi-method-parameter %}

{% api-method-parameter name="languages" type="array" required=false %}
Filter by languages
{% endapi-method-parameter %}

{% api-method-parameter name="tags\_included" type="array" required=false %}
Filter by tags to include
{% endapi-method-parameter %}

{% api-method-parameter name="tags\_excluded" type="array" required=false %}
Filter by tags to exclude
{% endapi-method-parameter %}

{% api-method-parameter name="ranges\_float" type="array" required=false %}
Filter by range floats
{% endapi-method-parameter %}

{% api-method-parameter name="ranges\_date" type="array" required=false %}
Filter by range dates
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Jobs successfully retrieved
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret key
{% endapi-method-response-example-description %}

```python
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
{% tab title="Python" %}
```python
from hrflow import Hrflow

client = Hrflow(api_secret="Your API Key", api_user="Your API user email")

client.job.scoring.list(board_keys=["board_key1", "board_key2"],
                          source_key="source_key", profile_key="profile_key", 
                          agent_key="agent_key", use_agent=1
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

