---
description: This endpoint allows you to index new Profile object.
---

# POST: /profile/indexing

Please find below an example of Json profile that could be submitted.

```javascript
{
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
      "date_start":  2016-01-01T00:00:00,
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
```

{% api-method method="post" host="https://api.hrflow.ai" path="/v1/profile/indexing" %}
{% api-method-summary %}
/profile/indexing
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to post Json Profile.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token
{% endapi-method-parameter %}

{% api-method-parameter name="X-USER-EMAIL" type="string" required=true %}
User's email
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="source\_key" type="string" required=true %}
Source key
{% endapi-method-parameter %}

{% api-method-parameter name="consent\_algorithmic" type="object" required=true %}
Profile's consent
{% endapi-method-parameter %}

{% api-method-parameter name="created\_at" type="string" required=true %}
Created date as ISO
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=false %}
Profile's reference
{% endapi-method-parameter %}

{% api-method-parameter name="info" type="array" required=true %}
Profile's related info :  
{  
      "full\_name": XXX,  
      "first\_name": XXX,  
      "last\_name": XXX,  
      "email": XXX,  
      "phone": 20202020,  
      "gender": F,  
      "picture":  
      "location": {"text": null},  
      "summary": "Brief summary",  
      "urls" : {...}  
}
{% endapi-method-parameter %}

{% api-method-parameter name="experiences" type="array" required=true %}
Profile's experiences:  
\[{  
      "title": "EXP1",  
      "company": "HrFlow"  
      "description": "Exp description",  
      "location": {  
                       "text": "Paris",   
                       "lat": 48.8534 ,  
                       "lng": 2.3488},  
      "date\_start": {"iso8601": "2018-01-01T00:00:00"},  
      "date\_end": {"iso8601": "2018-07-01T00:00:00"}  
},  
...\]
{% endapi-method-parameter %}

{% api-method-parameter name="experiences\_duration" type="number" required=true %}
Experience's duration
{% endapi-method-parameter %}

{% api-method-parameter name="educations" type="array" required=true %}
Profile's educations:  
\[{  
      "title" : "EDU1",  
      "school": "HrFlow Academy",  
      "description": "Edu description",  
      "location": {  
                       "text": "Paris",  
                       "lat" : 48.8534,  
                       "lng": 2.3488},  
     "date\_start": { "iso8601": "2016-01-01T00:00:00"},  
     "date\_end": {"iso8601": "2018-01-01T00:00:00"}  
},  
...\]  
                          
{% endapi-method-parameter %}

{% api-method-parameter name="educations\_duration" type="number" required=true %}
Education's duration
{% endapi-method-parameter %}

{% api-method-parameter name="text" type="string" required=true %}
Profile's text
{% endapi-method-parameter %}

{% api-method-parameter name="text\_language" type="string" required=true %}
Text language
{% endapi-method-parameter %}

{% api-method-parameter name="skills" type="array" required=true %}
Profile's skills : \[{  
                              "name": "Python",   
                              "type": "hard",  
                              "value": 0.6},  
                              ...\]
{% endapi-method-parameter %}

{% api-method-parameter name="languages" type="array" required=true %}
Profile's languages \[{"name": "english", "value":1}, ...\]
{% endapi-method-parameter %}

{% api-method-parameter name="interests" type="array" required=true %}
Profile's interests \[{"name": "e-sport", "value": 0.8},...\]
{% endapi-method-parameter %}

{% api-method-parameter name="labels" type="array" required=true %}
Profile's labels \[{  
                              "stage": "yes",   
                              "job\_key": job\_key,  
                              "date\_stage": "2020-07-07T00:00:00",  
                              "rating": 5,  
                              "date\_rating" : "2020-07-06T00:00:00"},  
                           ...\]
{% endapi-method-parameter %}

{% api-method-parameter name="tags" type="array" required=true %}
Profile's tags \[{"name": "archive", "value": true}, ...\]
{% endapi-method-parameter %}

{% api-method-parameter name="metadatas" type="array" required=true %}
Profile's metadatas \[{"name": "meta", "value": "file"}, ...\]
{% endapi-method-parameter %}

{% api-method-parameter name="attachments" type="array" required=true %}
Profile's attachments
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```bash
{
    "code": 201,
    "message": "Profile created",
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
            "name": "source name",
            "type": "api",
            "subtype": "http_api"
        },
        "updated_at": "2020-07-29T11:45:37+0000",
        "created_at": "2020-07-29T11:45:37+0000",
        "info": {
            "full_name": "Harry Potter",
            "first_name": "Harry",
            "last_name": "Potter",
            "email": "harry.potter@gmail.com",
            "phone": "0202",
            "location": {
                "text": null,
                "lat": null,
                "lng": null,
                "gmaps": null,
                "fields": null
            },
            "urls": {
                "from_resume": [],
                "linkedin": "",
                "twitter": "",
                "facebook": "",
                "github": "",
                "picture": ""
            },
            "picture": null,
            "gender": null,
            "summary": "Brief summary"
        },
        "text_language": null,
        "text": null,
        "experiences_duration": 5,
        "educations_duration": 4,
        "experiences": [
            {
                "key": "c4ade5ca8f3ebab04acc5e91fde5f9bb400d60cb",
                "title": "Lead",
                "description": "Developping.",
                "location": {
                    "text": "Paris",
                    "lat": null,
                    "lng": null,
                    "gmaps": null,
                    "fields": null
                },
                "date_start": "2018-01-01T00:00:00",
                "date_end": "2018-07-01T00:00:00",
                "hard_skills": null,
                "soft_skills": null,
                "company": "Mathematic Departement"
            }
        ],
        "educations": [
            {
                "key": "3ea49b56c3dc6e4a0bde8bc2ca159560e1f57cb5",
                "title": "Mathematicien",
                "description": "Description",
                "location": {
                    "text": "Scotland",
                    "lat": "lat",
                    "lng": "lng",
                    "gmaps": null,
                    "fields": null
                },
                "date_start": "2016-01-01T00:00:00",
                "date_end": "2018-01-01T00:00:00",
                "hard_skills": null,
                "soft_skills": null,
                "school": "University"
            }
        ],
        "attachments": [],
        "skills": [
            {
                "name": "manual skill",
                "type": "hard",
                "value": null
            },
            {
                "name": "Creative spirit",
                "type": "soft",
                "value": null
            },
            {
                "name": "Writing skills",
                "type": "hard",
                "value": null
            },
            {
                "name": "Communication",
                "type": "soft",
                "value": null
            }
        ],
        "languages": [
            {
                "name": "english",
                "value": null
            }
        ],
        "interests": [
            {
                "name": "football",
                "value": null
            }
        ],
        "labels": [
            {
                "stage": "yes",
                "job_key": "job_key"
            }
        ],
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
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```bash
{
    "code": 400,
    "message": "Invalid source fields"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Example

{% tabs %}
{% tab title="Python" %}
```python
from hrflow import Hrflow

client = Hrflow(api_secret="Your API Key", api_user="Your API user email")

data = {
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
      "date_start":  {"iso8601": "2018-01-01T00:00:00"},
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
};

client.profile.indexing.add_json(source_key="source_key", profile_json=data)
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';
const client = new Hrflow({
    api_secret: 'Your API Key',
    api_user: 'Your API user email',
});

const data = {
  'consent_algorithmic': {
            'owner': {
                'parsing': true,
                'revealing': false,
                'embedding': true,
                'searching': false,
                'scoring': true,
                'reasoning': false
            },
            'controller': {
                'parsing': true,
                'revealing': false,
                'embedding': true,
                'searching': false,
                'scoring': true,
                'reasoning': false
            }
        },
  'info' : {
      'full_name':'Harry Potter',
      'first_name': 'Harry',
      'last_name': 'Potter',
      'email':'harry.potter@gmail.com',
      'phone':'0202',
      'gender': null,
      'urls': {
          'from_resume': [],
          'linkedin': '',
          'twitter': '',
          'facebook': '',
          'github': '',
          'picture': ''},
      'picture': null,
  	  'location':{'text': null},
  	  'summary': 'Brief summary'
  },
  'experiences': [{
      'date_start':  {'iso8601': '2018-01-01T00:00:00'},
      'date_end': {'iso8601': '2018-07-01T00:00:00'},
      'title': 'Lead',
      'company': 'Mathematic Departement',
      'location': {'text':'Paris'},
      'description': 'Developping.'
      }],
  'experiences_duration':5,
  'educations': [{
      'date_start': {'iso8601': '2016-01-01T00:00:00'},
      'date_end': {'iso8601': '2018-01-01T00:00:00'},
      'title': 'Mathematicien',
      'school': 'University',
      'description': 'Description',
      'location': {'text':'Scotland', 'lat':'lat', 'lng': 'lng'}
  }],
  'educations_duration':4,
  'skills': [{'name':'manual skill', 'type': 'hard', 'value': null},
               {'name':'Creative spirit', 'type': 'soft','value': null}, 
               {'name':'Writing skills', 'type': 'hard','value': null}, 
               {'name':'Communication', 'type': 'soft','value': null}],
  'languages' : [{'name':'english', 'value': null}],
  'interests': [{'name':'football', 'value': null}],
  'tags':[{'name':'archive', 'value': false}],
  'metadatas':[],
  'labels':[{'stage':'yes', 'job_key':'job_key'}],
  'attachments': []
};

client.profile.indexing.addJson('source_key', data).then(response => {
    console.log(respone);
    // ...
});
```
{% endtab %}
{% endtabs %}

