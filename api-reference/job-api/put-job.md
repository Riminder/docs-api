---
description: This endpoint allows you to update an existing Job.
---

# PUT: /job/indexing

{% hint style="info" %}
This endpoint requires at least a job key and board\_key.
{% endhint %}

{% api-method method="put" host="https://api.hrflow.ai" path="/v1/job/indexing" %}
{% api-method-summary %}
Put Job
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to update an existing job.
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

{% api-method-body-parameters %}
{% api-method-parameter name="board\_key" type="string" required=true %}
Board's key
{% endapi-method-parameter %}

{% api-method-parameter name="key" type="string" required=true %}
Job's key
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=false %}
Job's reference
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
Job's name
{% endapi-method-parameter %}

{% api-method-parameter name="agent\_key" type="string" required=false %}
Agent key
{% endapi-method-parameter %}

{% api-method-parameter name="created\_at" type="string" required=true %}
Creation date in iso format
{% endapi-method-parameter %}

{% api-method-parameter name="url" type="string" required=true %}
Job's url
{% endapi-method-parameter %}

{% api-method-parameter name="summary" type="string" required=true %}
Job's summary
{% endapi-method-parameter %}

{% api-method-parameter name="sections" type="array" required=true %}
Job's sections
{% endapi-method-parameter %}

{% api-method-parameter name="location" type="array" required=true %}
Job's location
{% endapi-method-parameter %}

{% api-method-parameter name="skills" type="array" required=true %}
Job's skills
{% endapi-method-parameter %}

{% api-method-parameter name="languages" type="array" required=true %}
Job's languages
{% endapi-method-parameter %}

{% api-method-parameter name="tags" type="array" required=true %}
Job's tags
{% endapi-method-parameter %}

{% api-method-parameter name="metadatas" type="array" required=true %}
Job's metadatas
{% endapi-method-parameter %}

{% api-method-parameter name="ranges\_float" type="array" required=true %}
Job's ranges float
{% endapi-method-parameter %}

{% api-method-parameter name="ranges\_date" type="array" required=true %}
Job's ranges date
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Job successfully updated
{% endapi-method-response-example-description %}

```python
{
    "code": 201,
    "message": "Job created",
    "data": {
        "id": 2954,
        "key": "job_key",
        "reference": "Job's reference abcd",
        "name": "Data Engineer",
        "url": "https://www.pole-emploi.ai/jobs/data_engineer",
        "summary": "As an engineer for the Data Engineering Infrastructure team, you will design, build, scale, and evolve our data engineering platform, services and tooling. Your work will have a critical  impact on all areas of business: powering core data pipelines, supporting detailed internal analytics, calculating customer usage, securing our platform, and much more.",
        "sections": [
            {
                "name": "profile",
                "title": "Searched Profile",
                "description": "Bac+5"
            }
        ],
        "location": {
            "text": null,
            "lat": null,
            "lng": null,
            "gmaps": null,
            "fields": null
        },
        "skills": [
            {
                "name": "python",
                "value": null
            },
            {
                "name": "spark",
                "value": 0.90000000000000002
            }
        ],
        "languages": [
            {
                "name": "english",
                "value": 1
            },
            {
                "name": "french",
                "value": 1
            }
        ],
        "tags": [
            {
                "name": "archive",
                "value": true
            },
            {
                "name": "tag example",
                "value": "tag"
            }
        ],
        "ranges_float": [
            {
                "name": "salary",
                "value_min": 30,
                "value_max": 40,
                "unit": "eur"
            }
        ],
        "ranges_date": [
            {
                "name": "Dates",
                "value_min": "2020-05-18T21:59",
                "value_max": "2020-09-15T21:59"
            }
        ],
        "status": true,
        "archive": false,
        "members": [],
        "notification": false,
        "threshold": null,
        "updated_at": "2020-05-27T16:21:23+0000",
        "created_at": "2020-05-27T16:21:23+0000",
        "agent": {
            "id": "id",
            "key": "agent_key",
            "name": "test",
            "description": "description",
            "classifierVersion": "1584961482.484944",
            "classifier": {
                "id": "id",
                "key": "a2e8f27d9a3fc6aeb4e61fa390ecfd2b7564f8d8",
                "name": "General Model",
                "description": "Trained with our custom datasets of resumes, the General Model computes matching scores between a given job and a given profile. This model reaches an AUC (Area Under the Curve) up to 92.7% and handles both many (profiles) to one (job) and one (profile) to many (jobs) scoring.",
                "version": "1584961482.484944",
                "metric": 0.93700000000000006,
                "updated_at": null,
                "created_at": "2020-03-23T15:56:05+0000"
            },
            "user": {
                "id": 6,
                "email": "user@mail.com",
                "pseudo": "user",
                "firstName": "User",
                "lastName": "USER",
                "avatarUrl": "../uploads/user/avatar/bbeffd9082fc796feee52b15c42bec5215e3313c.png",
                "locale": "english",
                "position": "Lead Software Engineer",
                "phone": null
            },
            "archive": false,
            "updated_at": "2020-05-14T17:43:22+0000",
            "created_at": "2020-05-14T17:43:22+0000"
        },
        "query": []
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

data = {
    "name": "Data Engineer",
    "agent_key": "agent_key",
    "reference": "Job's reference abc",
    "url": "https://www.pole-emploi.ai/jobs/data_engineer",
    "summary": """As an engineer for the Data Engineering Infrastructure team,
                you will design, build, scale, and evolve our data engineering
                platform, services and tooling. Your work will have a critical 
                impact on all areas of business: powering core data pipelines,
                supporting detailed internal analytics, calculating customer
                usage, securing our platform, and much more.""",
    "location": {
                  "text": "Dampierre en Burly (45)",
                  "geopoint": {
                      "lat": 47.7667,
                      "lon": 2.5167
                  }
                 },
    "sections": [{
                    "name": "profile",
                    "title": "Searched Profile",
                    "description": "Bac+5"
                  }],
    "skills": [{
                  "name": "python",None               },
               {
                  "name": "spark",
                  "value": 0.9
               }],
    "languages": [{
                     "name": "english",
                     "value": 1
                  },
                 {  
                     "name": "french",
                     "value": 1
                  }],
    "tags": [{
                "name": "archive",
                "value": False
             },
             {  
                "name": "tag example",
                "value": "tag"
              }],
    "ranges_date": [{
                       "name": "Dates",
                       "value_min": "2020-05-18T21:59",
                       "value_max": "2020-09-15T21:59"
                    }],
    "ranges_float": [{
                       "name": "salary",
                       "value_min": 30,
                       "value_max": 40,
                       "unit": "eur"
                    }],
    "metadatas": [{
                     "name": "metadata example",
                     "value": "metadata"
                  }],
}

client.job.indexing.add_json(board_key="board_key", key="job_key", job_json=data)
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';
const client = new Hrflow({ 
    api_secret: "Your API Key",
    api_user: "Your API user email" 
});

client.job.indexing.edit("board_key", "job_key", {
    "name": "Data Engineer",
    "agent_key": "agent_key",
    "reference": "Job's reference abc",
    "url": "https://www.pole-emploi.ai/jobs/data_engineer",
    "summary": "As an engineer for the Data Engineering Infrastructure team,
                you will design, build, scale, and evolve our data engineering
                platform, services and tooling. Your work will have a critical 
                impact on all areas of business: powering core data pipelines,
                supporting detailed internal analytics, calculating customer
                usage, securing our platform, and much more.",
    "location": {
                  "text": "Dampierre en Burly (45)",
                  "geopoint": {
                      "lat": 47.7667,
                      "lon": 2.5167
                  }
                 },
    "sections": [{
                    "name": "profile",
                    "title": "Searched Profile",
                    "description": "Bac+5"
                  }],
    "skills": [{
                  "name": "python",
                  "value": null
               },
               {
                  "name": "spark",
                  "value": 0.9
               }],
    "languages": [{
                     "name": "english",
                     "value": 1
                  },
                 {  
                     "name": "french",
                     "value": 1
                  }],
    "tags": [{
                "name": "archive",
                "value": true
             },
             {  
                "name": "tag example",
                "value": "tag"
              }],
    "ranges_date": [{
                       "name": "Dates",
                       "value_min": "2020-05-18T21:59",
                       "value_max": "2020-09-15T21:59"
                    }],
    "ranges_float": [{
                       "name": "salary",
                       "value_min": 30,
                       "value_max": 40,
                       "unit": "eur"
                    }],
    "metadatas": [{
                     "name": "metadata example",
                     "value": "metadata"
                  }],
});
```
{% endtab %}
{% endtabs %}

