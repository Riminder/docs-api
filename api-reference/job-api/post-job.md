---
description: This endpoint allows you to add new Job to a given board.
---

# POST: /job/indexing

Please find below an example of JSON job that you can upload.

```bash
{
    "name": "Data Engineer",
    "agent_key": null,
    "reference": "Job's reference abc",
    "created_at": "2020-12-24T09:32:11",
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
                  }
                 },
    "sections": [{
                    "name": "profile",
                    "title": "Searched Profile",
                    "description": "Bac+5"
                  },
                  .
                  .
                  .
                  ],
    "skills": [{
                  "name": "python",
                  "value": null
               },
               {
                  "name": "spark",
                  "value": 0.9
               },
               .
               .
               .
               ],
    "languages": [{
                     "name": "english",
                     "value": 1
                  },
                 {  
                     "name": "french",
                     "value": 1
                  },
                  .
                  .
                  .
                  ],
    "tags": [{
                "name": "archive",
                "value": true
             },
             {  
                "name": "tag example",
                "value": "tag"
              },
              .
              .
              .
              ],
    "ranges_date": [{
                       "name": "Dates",
                       "value_min": "2020-05-18T21:59",
                       "value_max": "2020-09-15T21:59"
                    },
                    .
                    .
                    .
                    ],
    "ranges_float": [{
                       "name": "salary",
                       "value_min": 30,
                       "value_max": 40,
                       "unit": "eur"
                    },
                    .
                    .
                    .
                    ],
    "metadatas": [{
                     "name": "metadata example",
                     "value": "metadata"
                  },
                  .
                  .
                  .
                  ],
}
```

You can include complementary information such as :

* job's tags,
* job's metadata.

{% api-method method="post" host="https://api.hrflow.ai" path="/v1/job/indexing" %}
{% api-method-summary %}
Post /job/indexing
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to post job json.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token
{% endapi-method-parameter %}

{% api-method-parameter name="X-USER-EMAIL" type="string" required=true %}
User's email.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}

{% api-method-parameter name="board\_key" type="string" required=true %}
The key of the board in which the Job will be added
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
The Job's title
{% endapi-method-parameter %}

{% api-method-parameter name="agent\_key" type="string" required=false %}
The Agent unique identifier to attach to this Job
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=true %}
The Job's reference, it is unique for a given board
{% endapi-method-parameter %}

{% api-method-parameter name="created\_at" type="string" required=true %}
The creation date in iso Format
{% endapi-method-parameter %}

{% api-method-parameter name="url" type="string" required=true %}
The Job's url
{% endapi-method-parameter %}

{% api-method-parameter name="summary" type="string" required=true %}
A brief summary to describe missions and context of the Job
{% endapi-method-parameter %}

{% api-method-parameter name="sections" type="array" required=true %}
The Job's sections  
\(ie. \[{  
"name": "section\_name",  
"title": "section\_title",  
"description": "section\_description"}...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="location" type="object" required=true %}
Job's location  
\(ie. {  
"text": "xx rue XXXX" ,  
"lat":38.299637 ,  
"lng": -122.657535  
}\)
{% endapi-method-parameter %}

{% api-method-parameter name="skills" type="array" required=true %}
The Job's required skills  
\(ie. \[{"name": "skill", "type":"hard or soft", "value":0.8}, ...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="languages" type="array" required=true %}
The Job's required languages  
\(ie. \[{"name": "language", "value": 0.7}, ...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="tags" type="array" required=true %}
The Job's tags to include with the Job  
\(ie. \[{"name": "tag", "value":"tag\_value"}, ...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="metadatas" type="array" required=true %}
The Job's metadata  
\(ie. \[{"name": "meta", "value":"meta\_value"}, ...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="ranges\_float" type="array" required=true %}
The Job's ranges float  
\(ie. \[{  
'name': 'salary',  
'unit': 'eur',  
'value\_max': 50,  
'calue\_min': 30} ...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="ranges\_date" type="array" required=true %}
The Job's ranges date  
\(ie. \[{  
'name': 'dates',  
'value\_max': '2020-09-15T21:59',  
'value\_min': '2020-05-18T21:59'}...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="tasks" type="array" required=false %}
Tasks required in the job : \[{"name": "Ensure product delivery time", "value": null"}\]
{% endapi-method-parameter %}

{% api-method-parameter name="courses" type="array" required=false %}
Courses related to the job : \[{"name": "Statistics", "value": null"}\]
{% endapi-method-parameter %}

{% api-method-parameter name="certifications" type="array" required=false %}
Certifications mentionned in the job : \[{"name": "CCNA",   
"value": null}\]
{% endapi-method-parameter %}


{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Job successfully created.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 201,
    "message": "Job created",
    "data": {
        "id": id,
        "key": "job_key",
        "reference": "Job's reference 12",
        "name": "Data Engineer",
        "url": "https://www.pole-emploi.ai/jobs/data_engineer",
        "summary": "As an engineer for the Data Engineering Infrastructure team, you will design, build, scale, and evolve our data engineering platform, services and tooling. Your work will have a critical  impact on all areas of business: powering core data pipelines,  supporting detailed internal analytics, calculating customer  usage, securing our platform, and much more.",
        "sections": [
            {
                "name": "profile",
                "title": "Searched Profile",
                "description": "Bac+5"
            }
        ],
        "location": {
            "text": "Dampierre en Burly (45)",
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
        "updated_at": "2020-06-11T14:43:29+0000",
        "created_at": "2020-06-11T14:43:29+0000"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret key.
{% endapi-method-response-example-description %}

```bash
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxxx "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.hrflow.ai" path="/v1/job/indexing" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="courses" type="array" required=false %}
\[{"name": "Statistics", "value": null"}\]
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.hrflow.ai" path="/v1/job/indexing" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="courses" type="array" required=false %}
 \[{"name": "Statistics", "value": null"}\]
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.hrflow.ai" path="/v1/job/indexing" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="courses" type="array" required=false %}
 \[{"name": "Statistics", "value": null"}\]
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.hrflow.ai" path="/v1/profile/indexing" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="certifications" type="array" required=true %}
Profile's certifications : \[{  
"name": "CCNA",  
"value": null},  
...\]
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.hrflow.ai" path="/v1/profile/indexing" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="certifications" type="array" required=true %}
Profile's certifications : \[{  
"name": "CCNA",  
"value": null},  
...\]
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

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

job_json = {
    "name": "Data Engineer",
    "agent_key": None,
    "reference": "123",
    "created_at": "2020-12-24T09:32:11",
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
                  "name": "python",
                  "value": None},
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
                "value": True
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

client.job.indexing.add_json(board_key="board_key", job_json=job_json)
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';
const client = new Hrflow({ 
    api_secret: "Your API Key",
    api_user: "Your API user email" 
});

client.job.indexing.addJosn("board_key", {
    "name": "Data Engineer",
    "agent_key": None, #Scoring engine
    "reference": "123",
    "created_at": "2020-12-24T09:32:11",
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

