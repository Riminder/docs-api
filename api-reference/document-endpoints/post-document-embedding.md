---
description: This endpoint allows you to generate item \(profile or job\) embedding.
---

# POST: /document/embedding

{% hint style="info" %}
**item** must have the same shape as defined for [profile](https://developers.hrflow.ai/api-reference/profile-api/post-profile-indexing) or [job](https://developers.hrflow.ai/api-reference/job-api/post-job)
{% endhint %}

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/document/embedding/" method="post" summary="Post /document/embedding" %}
{% swagger-description %}
This endpoint allows you to generate item (profile or job) embedding.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="item_type" type="string" %}
profile or job
{% endswagger-parameter %}

{% swagger-parameter in="body" name="item" type="string" %}
profile_json or job_json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="return_sequences" type="string" %}
True or False (default behavior is False)
{% endswagger-parameter %}

{% swagger-response status="200" description="Item's embedding is generated successfully." %}
```bash
{ 
    "code": 200,
    "message": "Embedding results",
    "data": "embeddings_encoded_base64"
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Invalid Item type" %}
```bash
{
    "code": 400,
    "message": "Invalid Item Type: "
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Invalid secret key: xxxx" %}
```bash
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxxx "
}
```
{% endswagger-response %}
{% endswagger %}

## Embedding :

Embeddings are base64 encoded.

In order to retrieve embedding as **list\[list]**, the result must be decoded (base64) and reshaped (-1, 1024).\
Refer to `decode_float_list` below for implementation example .

{% tabs %}
{% tab title="Python" %}
```python
from hrflow import Hrflow
import base64
import numpy as np

dfloat32 = np.dtype('>f4')


def decode_float_list(base64_string):
    bytes = base64.b64decode(base64_string)
    np_array = np.frombuffer(bytes, dtype=dfloat32)
    return np.reshape(np_array, (-1, 1024)).tolist()


def encode_array(arr):
    base64_str = base64.b64encode(np.array(arr).astype(dfloat32)).decode("utf-8")
    return base64_str


client = Hrflow(api_secret="Your API Key", api_user="Your API user email")


profile_json = {
  "consent_algorithmic": {
            "owner": {
                "parsing": True,
                "revealing": False,
                "embedding": True,
                "searching": False,
                "scoring": True,
                "reasoning": False
            },
            "controller": {
                "parsing": True,
                "revealing": False,
                "embedding": True,
                "searching": False,
                "scoring": True,
                "reasoning": False
            }
        },
  "info" : {
      "full_name":"Harry Potter",
      "first_name": "Harry",
      "last_name": "Potter",
      "email":"harry.potter@gmail.com",
      "phone":"0202",
      "gender": None,
      "urls": {
          "from_resume": [],
          "linkedin":"",
          "twitter":"",
          "facebook":"",
          "github":"",
          "picture":""},
      "picture":None,
        "location":{"text": None},
        "summary": "Brief summary"
  },
  "experiences": [{
      "date_start":  "2016-01-01T00:00:00",
      "date_end": {"iso8601": "2018-07-01T00:00:00"},
      "title": "Lead",
      "company": "Mathematic Departement",
      "location": {"text":"Paris"},
      "description": "Developping."
      }],
  "experiences_duration":5,
  "educations": [{
      "date_start": {"iso8601": "2016-01-01T00:00:00"},
      "date_end": {"iso8601": "2018-01-01T00:00:00"},
      "title": "Mathematicien",
      "school": "University",
      "description": "Description",
      "location": {"text":"Scotland", "lat":"lat", "lng": "lng"}
  }],
  "educations_duration":4,
  "skills": [{"name":"manual skill", "type": "hard", "value": None},
               {"name":"Creative spirit", "type": "soft","value": None}, 
               {"name":"Writing skills", "type": "hard","value": None}, 
               {"name":"Communication", "type": "soft","value": None}],
  "languages" : [{"name":"english", "value": None}],
  "interests": [{"name":"football", "value": None}],
  "tags":[{"name":"archive", "value": False}],
  "metadatas":[],
  "labels":[{"stage":"yes", "job_key":"job_key"}],
  "attachments": []
}

response = client.document.embedding.post(item_type="profile", 
                                          item=profile_json,
                                          return_sequences=True)

embedding = decode_float_list(response.get('data'))
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';
const client = new Hrflow({ 
    api_secret: 'Your API Key',
    api_user: 'Your API user email'
});

const profile_json = {
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
  "info" : {
      "full_name":"Harry Potter",
      "first_name": "Harry",
      "last_name": "Potter",
      "email":"harry.potter@gmail.com",
      "phone":"0202",
      "gender": null,
      "urls": {
          "from_resume": [],
          "linkedin":"",
          "twitter":"",
          "facebook":"",
          "github":"",
          "picture":""},
      "picture":null,
        "location":{"text": null},
        "summary": "Brief summary"
  },
  "experiences": [{
      "date_start":  "2016-01-01T00:00:00",
      "date_end": {"iso8601": "2018-07-01T00:00:00"},
      "title": "Lead",
      "company": "Mathematic Departement",
      "location": {"text":"Paris"},
      "description": "Developping."
      }],
  "experiences_duration":5,
  "educations": [{
      "date_start": {"iso8601": "2016-01-01T00:00:00"},
      "date_end": {"iso8601": "2018-01-01T00:00:00"},
      "title": "Mathematicien",
      "school": "University",
      "description": "Description",
      "location": {"text":"Scotland", "lat":"lat", "lng": "lng"}
  }],
  "educations_duration":4,
  "skills": [{"name":"manual skill", "type": "hard", "value": null},
               {"name":"Creative spirit", "type": "soft","value": null}, 
               {"name":"Writing skills", "type": "hard","value": null}, 
               {"name":"Communication", "type": "soft","value": null}],
  "languages" : [{"name":"english", "value": null}],
  "interests": [{"name":"football", "value": null}],
  "tags":[{"name":"archive", "value": false}],
  "metadatas":[],
  "labels":[{"stage":"yes", "job_key":"job_key"}],
  "attachments": []
}


client.document.embedding.post("profile", profile_json, true).then(response => {
    console.log(response);
    // ...
});
```
{% endtab %}
{% endtabs %}
