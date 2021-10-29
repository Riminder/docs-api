---
description: This endpoint allows you to update an existing Job.
---

# PUT: /job/indexing

{% hint style="info" %}
This endpoint requires at least a job key and board\_key.
{% endhint %}

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/job/indexing" method="put" summary="Put Job" %}
{% swagger-description %}
This endpoint allows you to update an existing job.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
The Job's title
{% endswagger-parameter %}

{% swagger-parameter in="body" name="agent_key" type="string" %}
The Agent unique identifier to attach to this Job
{% endswagger-parameter %}

{% swagger-parameter in="body" name="reference" type="string" %}
The Job's reference, it is unique for a given board
{% endswagger-parameter %}

{% swagger-parameter in="body" name="created_at" type="string" %}
The creation date in iso Format
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" type="string" %}
The Job's url
{% endswagger-parameter %}

{% swagger-parameter in="body" name="summary" type="string" %}
A brief summary to describe missions and context of the Job
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sections" type="array" %}
The Job's sections

\


(ie. [{

\


"name": "section_name",

\


"title": "section_title",

\


"description": "section_description"}...])
{% endswagger-parameter %}

{% swagger-parameter in="body" name="location" type="object" %}
Job's location

\


(ie. {

\


"text": "xx rue XXXX" ,{

\


"lat":38.299637 ,

\


"lng": -122.657535

\


})
{% endswagger-parameter %}

{% swagger-parameter in="body" name="skills" type="array" %}
The Job's required skills

\


(ie. [{"name": "skill", "type":"hard or soft", "value":0.8}, ...])
{% endswagger-parameter %}

{% swagger-parameter in="body" name="languages" type="array" %}
The Job's required languages

\


(ie. [{"name": "language", "value": 0.7}, ...])
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tags" type="array" %}
The Job's tags to include with the Job

\


(ie. [{"name": "tag", "value":"tag_value"}, ...])
{% endswagger-parameter %}

{% swagger-parameter in="body" name="metadatas" type="array" %}
The Job's metadata

\


(ie. [{"name": "meta", "value":"meta_value"}, ...])
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ranges_float" type="array" %}
The Job's ranges float

\


(ie. [{

\


'name': 'salary',

\


'unit': 'eur',

\


'value_max': 50,

\


'calue_min': 30} ...])
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ranges_date" type="array" %}
The Job's ranges date

\


(ie. [{

\


'name': 'dates',

\


'value_max': '2020-09-15T21:59',

\


'value_min': '2020-05-18T21:59'}...])
{% endswagger-parameter %}

{% swagger-response status="200" description="Job successfully updated" %}
```python
{
    "code": 200,
    "message": "Job edited",
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
        "updated_at": "2020-05-14T17:43:22+0000",
        "created_at": "2020-05-14T17:43:22+0000"
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
                  "lat": 47.7667,
                  "lng": 2.5167
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
                "name": "tag example",
                "value": False
             },
             {  
                "name": "tag2 example",
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

client.job.indexing.edit(board_key="board_key", key="job_key", job_json=data)
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
                  "lat": 47.7667,
                  "lng": 2.5167
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
