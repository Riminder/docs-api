# \[POST\] /document/embedding

{% hint style="info" %}
**item** must have the same shape as defined for [profile](https://developers.hrflow.ai/api-reference/profile-api/post-profile-indexing) or [job](https://developers.hrflow.ai/api-reference/job-api/post-job)
{% endhint %}

{% api-method method="post" host="https://api.hrflow.ai" path="/v1/document/embedding/" %}
{% api-method-summary %}
Post /document/embedding
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to generate item \(profile or job\) embedding.
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
{% api-method-parameter name="item\_type" type="string" required=true %}
profile or job
{% endapi-method-parameter %}

{% api-method-parameter name="item" type="string" required=true %}
profile\_json or job\_json
{% endapi-method-parameter %}

{% api-method-parameter name="return\_sequences" type="string" required=false %}
True or False \(default behavior is False\)
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Item's embedding is generated successfully.
{% endapi-method-response-example-description %}

```bash
{ 
    "code": 200,
    "message": "Embedding results",
    "data": "embeddings_encoded_base64"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid Item type
{% endapi-method-response-example-description %}

```bash
{
    "code": 400,
    "message": "Invalid Item Type: "
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret key
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



## Embedding :

Embedding's results are encoded \(base64\).

In order to get embedding as **list\[list\]**, results must be decoded \(base64\) to get binary format of item's embedding, then based on this binary, numpy array could be generated and reshaped \(-1, 1024\). 

{% tabs %}
{% tab title="Python" %}
```python
import hrflow as hf
import base64
import numpy as np

dfloat32 = np.dtype('>f4')


def decode_float_list(base64_string):
    bytes = base64.b64decode(base64_string)
    np_array = np.frombuffer(bytes, dtype=dfloat32)
    return np.reshape(embeddings, (-1, 1024)).tolist()


def encode_array(arr):
    base64_str = base64.b64encode(np.array(arr).astype(dfloat32)).decode("utf-8")
    return base64_str
    
    
client = hf.client(api_secret="Your API Key", api_user="Your API user email")


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
{% endtabs %}



