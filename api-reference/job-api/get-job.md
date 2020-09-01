---
description: Retrieve Job
---

# GET: /job/indexing

{% hint style="info" %}
This endpoint requires at least a job key and board\_key.
{% endhint %}

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/job/indexing" %}
{% api-method-summary %}
Get Job
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get a job.
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

{% api-method-parameter name="key" type="string" required=false %}
Job key
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=false %}
Job reference
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Job successfully retrieved
{% endapi-method-response-example-description %}

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
import hrflow as hf

client = hf.client(api_secret="Your API Key", api_user="Your API user email")

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

