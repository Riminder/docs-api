---
description: Retrieve a list of jobs based on given filters
---

# GET: /jobs/searching

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
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token.
{% endapi-method-parameter %}

{% api-method-parameter name="X-USER-EMAIL" type="string" required=true %}
User's email.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="board\_keys" type="array" required=true %}
List of board keys
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
Total job to retrieve  
Default is 10
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="integer" required=false %}
API page offset  
Default is 1
{% endapi-method-parameter %}

{% api-method-parameter name="order\_by" type="string" required=false %}
Order by \(ie. desc, asc\)  
Default is "desc"
{% endapi-method-parameter %}

{% api-method-parameter name="sort\_by" type="string" required=false %}
Sort by \(ie. created\_at, searching, scoring\)  
Default is "created\_at"
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

{% api-method-parameter name="location\_geopoint" type="object" required=false %}
Filter by location's lattitude and longitude  
\(ie. {"lat"35.7516600: , "lon":10.7110900}\)
{% endapi-method-parameter %}

{% api-method-parameter name="location\_distance" type="number" required=false %}
Max radius
{% endapi-method-parameter %}

{% api-method-parameter name="summary\_keywords" type="array" required=false %}
Filter by summary keywords
{% endapi-method-parameter %}

{% api-method-parameter name="text\_keywords" type="array" required=false %}
Filter by text keywords
{% endapi-method-parameter %}

{% api-method-parameter name="skills" type="array" required=false %}
Filter by skills
{% endapi-method-parameter %}

{% api-method-parameter name="languages" type="array" required=false %}
Filter by languages
{% endapi-method-parameter %}

{% api-method-parameter name="tags\_included" type="array" required=false %}
Filter by tags
{% endapi-method-parameter %}

{% api-method-parameter name="ranges\_float" type="array" required=false %}
Filter by ranges float
{% endapi-method-parameter %}

{% api-method-parameter name="ranges\_date" type="array" required=false %}
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
    "message": "Job searching results",
    "meta": {
        "page": 1,
        "maxPage": 73,
        "count": 1,
        "total": 73
    },
    "data": {
        "jobs": [
            {
                "id": 4706,
                "key": "d224a0e830605ca7dddab20956624a1ca38d7e45",
                "reference": "STO00002082",
                "name": "ALTERNANT(E) MASTER ACHATS – SUPPLY CHAIN (F/H)",
                "url": null,
                "summary": null,
                "sections": [...],
                "location": {
                    "text": "France Île-de-France Bois-Colombes",
                    "lat": 48.913539999999998,
                    "lng": 2.2673299999999998,
                    "gmaps": null,
                    "fields": []
                },
                "skills": [],
                "languages": [],
                "tags": [...],
                "ranges_float": [],
                "ranges_date": [],
                "updated_at": "2020-06-09T12:39:57+0000",
                "created_at": "2020-04-07T17:39:52+0000"
            }
        ]
    }
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
{% tab title="Python" %}
```python
import hrflow as hf

client = hf.client(api_secret="Your API Key", api_user="Your API user email")

client.job.searching.list(board_keys=["board_key1", "board_key2"],
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

client.job.searching.list(["board_key1", "board_key2"],  {
    name: "data scientist",
    page: 1,
    limit: 10,
    order_by: "asc",
    sort_by: "created_at",
    text_keywords: ["engineer", "python"],
    tags_included: [[{name: "active", value: true}]],
    location_distance: 30,
    location_geopoint: {"lat":33.59662,"lng":-7.61889}
});

```
{% endtab %}
{% endtabs %}

