---
description: This endpoint allows you to retrieve an existing Job.
---

# GET: /job/indexing

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/job/indexing" method="get" summary="Get Job" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="board_key" type="string" %}
Board key
{% endswagger-parameter %}

{% swagger-parameter in="query" name="key" type="string" %}
Job' s key
{% endswagger-parameter %}

{% swagger-parameter in="query" name="reference" type="string" %}
Job's reference
{% endswagger-parameter %}

{% swagger-response status="200" description="Job successfully retrieved" %}
```python
{
    "code": 200,
    "message": "Job details",
    "data": {
        "id": id,
        "key": "job_key",
        "reference": "REF1",
        "name": "Technicien de maintenance H/F",
        "url": null,
        "summary": null,
        "sections": [
            {
                "name": "section's name",
                "title": "section's title",
                "description": "Section's description", 
        ],
        "location": {
            "text": "France Auvergne-Rhône-Alpes Alby-sur-Chéran",
            "lat": 45.817700000000002,
            "lng": 6.0221499999999999,
            "gmaps": null,
            "fields": []
        },
        "skills": [],
        "languages": [],
        "tags": [
            {
                "name": "company",
                "value": "alpha"
            },
            {
                "name": "responsibility",
                "value": "admin"
            },
            {
                "name": "category",
                "value": "Maintenance"
            },
            {
                "name": "type",
                "value": "CDI"
            },
            {
                "name": "education_level",
                "value": "Bac+5"
            },
            {
                "name": "professional_experience",
                "value": "Junior"
            }
        ],
        "ranges_float": [],
        "ranges_date": [],
        "updated_at": "2020-06-09T12:34:58+0000",
        "created_at": "2020-04-06T12:02:31+0000"
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

client.job.indexing.get(board_key="board_key",
                        key="job_key",
                        # OR
                        reference='job_reference')
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';
const client = new Hrflow({ 
    api_secret: "Your API Key",
    api_user: "Your API user email" 
});

client.job.indexing.get("board_key", {
    key: "job_key",
    // Or
    reference: "job_reference"
});
```
{% endtab %}
{% endtabs %}
