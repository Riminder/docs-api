---
description: This endpoint allows to retrieve  the Profile object.
---

# GET: /profile/indexing

One of key , reference or email parameters should be provided to identify the profile.

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/profile/indexing" method="get" summary="/profile/indexing" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email
{% endswagger-parameter %}

{% swagger-parameter in="query" name="source_key" type="string" %}
The source unique identifier
{% endswagger-parameter %}

{% swagger-parameter in="query" name="key" type="string" %}
The profile unique identifier
{% endswagger-parameter %}

{% swagger-parameter in="query" name="reference" type="string" %}
The profile's reference
{% endswagger-parameter %}

{% swagger-parameter in="query" name="email" type="string" %}
The profile's email
{% endswagger-parameter %}

{% swagger-response status="200" description="Profile object is successfully retrieved" %}
```bash
{
    "code": 200,
    "message": "Profile details",
    "data": {
        "id": id,
        "key": "profile_key",
        "reference": null,
        "archive": null,
        "consent_algorithmic": {
            "owner": {
                "parsing": true,
                "revealing": false,
                "embedding": true,
                "searching": false,
                "scoring": true,
                "reasoning": false
            },
            "controller": {
                "parsing": true,
                "revealing": false,
                "embedding": true,
                "searching": false,
                "scoring": true,
                "reasoning": false
            }
        },
        "source": {
            "id": id,
            "key": "source_key",
            "name": "Source name",
            "type": "dropzone",
            "subtype": "dropzone"
        },
        "updated_at": "2020-07-24T14:17:34+0000",
        "created_at": "2020-04-23T08:18:54+0000",
        "info": {
            "full_name": "Harry Potter",
            "first_name": "Harry",
            "last_name": "Potter",
            "date_birth": "1990-08-09T00:00:00+0000",
            "email": "harry.potter@hrflow.ai",
            "phone": null,
            "location": {
                "text": null,
                "lat": null,
                "lng": null,
                "gmaps": null,
                "fields": []
            },
            "urls": {
                "from_resume": [],
                "linkedin": "",
                "twitter": "",
                "facebook": "",
                "github": ""
            },
            "picture": "picture public url",   
            "gender": "male",
            "summary": "Brief summary"
        },
        "text_language": "fr",
        "text": "Harry Potter harry.potter@gmail.com 0202 Brief summary \
          Mathematic Departement Developping Mathematicien University Description \
          manual skill Creative spirit Writing skills Communication english football",
        "experiences_duration": 5.6447862760019998,
        "educations_duration": 0,
        "experiences": [
            {
                "key": "3bd7a3e409abd073dd29a9134d33348e35a9ee51",
                "title": "Analyste d'affaires",
                "description": "Livraison des solutions web transactionnels"
                "location": {
                    "text": "Montreal, QC, Canada",
                    "lat": 45.512410000000003,
                    "lng": -73.554689999999994,
                    "gmaps": null,
                    "fields": []
                },
                "date_start": "2017-08-01T00:00:00",
                "date_end": "1969-12-31T23:59:59",
                "company": "Banque Nationale",
                "certifications": [{"name": "certificate exp", "value": null}],
                "courses": [{"name": "course exp", "value": null}],
                "tasks": [{"name": "task exp", "value": null}],
                "skills": [{"name": "skill exp", "type" : "hard", "value": null}]
            }
        ],
        "educations": [
            {
                "key": "key",
                "title": "Developper",
                "description": "Web Developpement",
                "location": {
                    "text": null,
                    "lat": null,
                    "lng": null,
                    "gmaps": null,
                    "fields": []
                },
                "date_start": null,
                "date_end": null,
                "school": null,
                "certifications": [{"name": "certificate edu", "value": null}],
                "courses": [{"name": "course edu", "value": null}],
                "tasks": [{"name": "task edu", "value": null}],
                "skills": [{"name": "skill edu", "type" : "hard", "value": null}]
            }
        ],
        "attachments": [],
        "certifications": [
                {"name": "certificate", "value": null}
                ],
        "courses": [
                {"name": "course", "value": null}
                ],
        "tasks": [
                {"name": "task", "value": null}
                ],
        "skills": [{"name":"manual skill", "type": "hard", "value": null},
                    {"name":"Creative spirit", "type": "soft", "value": null}, 
                    {"name":"Writing skills", "type": "hard", "value": null}, 
                    {"name":"Communication", "type": "soft", "value": null}],
        "languages": [],
        "interests": [],
        "labels": [],
        "tags": [
            {
                "name": "archive",
                "value": false
            }
        ],
        "metadatas": []
    }
}
```
{% endswagger-response %}

{% swagger-response status="400" description="" %}
```bash
{
    "code": 400,
    "message": "Invalid source fields"
}
```
{% endswagger-response %}
{% endswagger %}

## Example

{% tabs %}
{% tab title="Python" %}
```python
from hrflow import Hrflow

client = Hrflow(api_secret="Your API Key", api_user="Your API user email")

client.profile.indexing.get(source_key="source_key",
                            key="profile_key",
                            # OR
                            reference='profile_reference',
                            # OR
                            email='example@example.com')
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';

const client = new Hrflow({ 
    api_secret: 'Your API Key',
    api_user: 'Your API user email' 
});

client.profile.indexing.get('source_key', {
    key: 'profile_key',
    // or
    reference: 'profile_reference'
    // or
    email: 'example@example.com',   
}).then(response => {
    console.log(response);
    // ...
});
```
{% endtab %}
{% endtabs %}
