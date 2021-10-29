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
      "date_birth": "1990-08-09T00:00:00+0000"
      "email":"harry.potter@gmail.com",
      "phone":"0202",
      "gender": null,
      "urls": {
          "from_resume": [],
          "linkedin":"",
          "twitter":"",
          "facebook":"",
          "github":""},
      "picture": "picture public url",
      "location":{"text": null},
      "summary": "Brief summary"
  },
  "text": "Harry Potter harry.potter@gmail.com 0202 Brief summary \
          Mathematic Departement Developping Mathematicien University Description \
          manual skill Creative spirit Writing skills Communication english football",
  "experiences": [{
      "date_start": {"iso8601": "2016-01-01T00:00:00"},
      "date_end": {"iso8601": "2018-07-01T00:00:00"},
      "title": "Lead",
      "company": "Mathematic Departement",
      "description": "Developping."
      "location": {"text":"Paris"},
      "certifications": [{
            "name": "certificate exp",
            "value": null
        }],
       "courses": [{
            "name": "course exp",
            "value": null
        }],
       "tasks": [{
            "name": "task exp",
            'value': null
        }],
       "skills": [{
            "name": "skill exp",
            "value": null,
            "type" : "hard"
        }]
      }],
  "experiences_duration":5,
  "educations": [{
      "date_start": {"iso8601": "2016-01-01T00:00:00"},
      "date_end": {"iso8601": "2018-01-01T00:00:00"},
      "title": "Mathematicien",
      "school": "University",
      "description": "Description",
      "location": {"text":"Scotland", "lat":"lat", "lng": "lng"},
      "certifications": [{
            "name": "certificate edu",
            "value": null
        }],
      "courses": [{
            "name": "course edu",
            "value": null
        }],
      "tasks": [{
            "name": "task edu",
            "value": null
        }],
      "skills": [{
            "name": "skill edu",
            "value": null,
            "type" : "hard"
        }]
  }],
  "educations_duration":4,
  "certifications": [
        {"name": "certificate exp", "value": null},
        {"name": "certificate edu", "value": null}
        ],
  "courses": [
        {"name": "course exp", "value": null},
        {"name": "cours edu", "value": null}],
  "tasks": [
        {"name": "task exp", "value": null},
        {"name": "task edu", "value": null}],
  "skills": [{"name":"manual skill", "type": "hard", "value": null},
            {"name":"Creative spirit", "type": "soft", "value": null}, 
            {"name":"Writing skills", "type": "hard", "value": null}, 
            {"name":"Communication", "type": "soft", "value": null},
            {"name": "skill edu", 'value': null, "type": "hard"}
            {"name": "skill exp", 'value': null, "type": "hard"}],
  "languages" : [{"name":"english", "value": null}],
  "interests": [{"name":"football", "value": null}],
  "tags":[{"name":"archive", "value": false}],
  "metadatas":[],
  "labels":[{"stage":"yes", "job_key":"job_key"}],
  "attachments": []
}
```

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/profile/indexing" method="post" summary="/profile/indexing" %}
{% swagger-description %}
This endpoint allows you to post Json Profile.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email
{% endswagger-parameter %}

{% swagger-parameter in="body" name="source_key" type="string" %}
The key of the source in which the Profile will be added
{% endswagger-parameter %}

{% swagger-parameter in="body" name="consent_algorithmic" type="object" %}
The user's algorithmic consent, it tells to the algorithm what are the allowed actions in order to use personal data
{% endswagger-parameter %}

{% swagger-parameter in="body" name="created_at" type="string" %}
The Creation datetime in iso format
{% endswagger-parameter %}

{% swagger-parameter in="body" name="reference" type="string" %}
Profile's reference, it is a unique for a given source
{% endswagger-parameter %}

{% swagger-parameter in="body" name="info" type="array" %}
Profile's related info :

\


{

\


"full_name": "XXX",

\


"first_name": "XXX",

\


"last_name": "XXX", "date_birth": "XX-XX-XXXXTXX:XX:XX", "email": "XXX",

\


"phone": "20202020",

\


"gender": "female",

\


"picture":

\


"location": {"text": null},

\


"summary": "Brief summary",

\


"urls" : {...}

\


}
{% endswagger-parameter %}

{% swagger-parameter in="body" name="educations" type="array" %}
Profile's educations:

\


\[{

\


"title" : "EDU1",

\


"school": "HrFlow Academy",

\


"description": "Edu description",

\


"location": {

\


"text": "Paris",

\


"lat" : 48.8534,

\


"lng": 2.3488},

\


"date_start": { "iso8601": "2016-01-01T00:00:00"},

\


"date_end": {"iso8601": "2018-01-01T00:00:00"}

\


},

\


...]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="educations_duration" type="number" %}
The Education's duration
{% endswagger-parameter %}

{% swagger-parameter in="body" name="experiences" type="array" %}
Profile's experiences:

\


\[{

\


"title": "EXP1",

\


"company": "HrFlow"

\


"description": "Exp description",

\


"location": {

\


"text": "Paris",

\


"lat": 48.8534 ,

\


"lng": 2.3488},

\


"date_start": {"iso8601": "2018-01-01T00:00:00"},

\


"date_end": {"iso8601": "2018-07-01T00:00:00"}

\


},

\


...]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="experiences_duration" type="number" %}
The profile's seniority.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="text" type="string" %}
A text to include with a Profile, it describes concisely each experience and education.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="text_language" type="string" %}
The language of the original text, it is in ISO 639-1 format
{% endswagger-parameter %}

{% swagger-parameter in="body" name="certifications" type="array" %}
Profile's certifications : [{

\


"name": "CCNA",

\


"value": null},

\


...]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="courses" type="array" %}
Profile's courses : [{

\


"name": "Big Data", "value": null},

\


...]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tasks" type="array" %}
Profile's tasks : [{

\


"name": "task",

\


"value": null},

\


...]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="skills" type="array" %}
Profile's skills : [{

\


"name": "Python",

\


"type": "hard",

\


"value": 0.6},

\


...]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="languages" type="array" %}
The Profile's languages [{"name": "english", "value":1}, ...]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="interests" type="array" %}
The Profile's interests [{"name": "e-sport", "value": 0.8},...]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="labels" type="array" %}
The Profile's labels [{

\


"stage": "yes",

\


"job_key": job_key,

\


"date_stage": "2020-07-07T00:00:00",

\


"rating": 5,

\


"date_rating" : "2020-07-06T00:00:00"},

\


...]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tags" type="array" %}
The Profile's tags [{"name": "archive", "value": true}, ...]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="metadatas" type="array" %}
Profile's metadatas [{"name": "meta", "value": "file"}, ...]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="attachments" type="array" %}
Profile's attachments
{% endswagger-parameter %}

{% swagger-response status="201" description="Cake successfully retrieved." %}
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
            "date_birth": "1990-08-09T00:00:00+0000"
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
                "company": "Mathematic Departement";
                "certifications": [{
                        "name": "certificate exp",
                        "value": null
                    }],
                "courses": [{
                        "name": "cours exp",
                        "value": null
                    }],
                "tasks": [{
                        "name": "tache exp",
                        "value": null
                    }],
                "skills": [{
                        "name": "skill exp",
                        "value": null,
                        "type" : "hard"
                    }]         
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
                "school": "University",
                "certifications": [{
                        "name": "certificate edu",
                        "value": null
                    }],
                "courses": [{
                        "name": "cours edu",
                        "value": null
                    }],
                "tasks": [{
                        "name": "tache edu",
                        'value': null
                    }],
                "skills": [{
                        "name": "skill edu",
                        "value": null,
                        "type" : "hard"
                    }]
            }
        ],
        "attachments": [],
        "certifications": [
                {"name": "certificate exp", "value": null},
                {"name": "certificate edu", "value": null}
                ],
        "courses": [
                {"name": "cours exp", "value": null},
                {"name": "cours edu", "value": null}],
        "tasks": [
                {"name": "tache exp", "value": null},
                {"name": "tache edu", "value": null}],
        "skills": [
                {"name":"manual skill", "type": "hard", "value": null},
                {"name":"Creative spirit", "type": "soft", "value": null}, 
                {"name":"Writing skills", "type": "hard", "value": null}, 
                {"name":"Communication", "type": "soft", "value": null},
                {"name": "skill edu", 'value': null, "type": "hard"}
                {"name": "skill exp", 'value': null, "type": "hard"}],
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
{% endswagger-response %}

{% swagger-response status="400" description="Could not find a cake matching this query." %}
```bash
{
    "code": 400,
    "message": "Invalid source fields"
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="danger" %}
It is highly recommended to post the profile with a **text** field combining First Name / Last Name , Summary and education / experience 's description.
{% endhint %}

{% hint style="danger" %}
**date\_start** and **date\_end** in Experience and Education are objects, or conversely the [GET](https://developers.hrflow.ai/api-reference/profile-api/get-profile-indexing) endpoint sends you back **date\_start** and **date\_end** as **string**

```python
{"iso8601" : "2018-01-01T00:00:00"}
```
{% endhint %}

## Example

{% tabs %}
{% tab title="Python" %}
```python
from hrflow import Hrflow

client = Hrflow(api_secret="Your API Key", api_user="Your API user email")

data = {
    "reference" : "my_profile",
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
      "full_name":"John Doe",
      "first_name": "John",
      "last_name": "Doe",
      "date_birth": "1990-08-09T00:00:00+0000",
      "email":"john.doe@gmail.com",
      "phone":"0212787656",
      "gender": "Male",
      "urls": {
          "from_resume": [],
          "linkedin":"",
          "twitter":"",
          "facebook":"",
          "github":""},
      "picture": "picture public url",
      "location":{"text": None},
      "summary": "Brief summary"
  },
  "text": "In this section should be the bulk text of the \
          whole profile with all the sections",
  "experiences": [{
      "date_start": {"iso8601": "2016-01-01T00:00:00"},
      "date_end": {"iso8601": "2018-07-01T00:00:00"},
      "title": "Lead software engineer",
      "company": "HrFlow.ai",
      "description": "Developping backend web apps using Python and Django framework.",
      "location": {"text":"Paris"},
      "certifications": [{
            "name": "AWS cloud certification",
            "value": None
        }],
       "courses": [],
       "tasks": [{
            "name": "Continuous integration",
            'value': None
        }],
       "skills": [{
            "name": "Django",
            "value": None,
            "type" : "hard"
        }]
      }],
  "experiences_duration":2.5,
  "educations": [{
      "date_start": {"iso8601": "2016-01-01T00:00:00"},
      "date_end": {"iso8601": "2018-01-01T00:00:00"},
      "title": "Msc in software engineering",
      "school": "Ecole Centrale Paris",
      "description": "Education description text",
      "location": {"text":"Paris"},
      "certifications": [{
            "name": "certificate edu",
            "value": None
        }],
      "courses": [{
            "name": "Python programming",
            "value": None
        }],
      "tasks": [],
      "skills": []
  }],
  "educations_duration": 2,
  "certifications": [
        {"name": "certificate exp", "value": None},
        {"name": "certificate edu", "value": None}
        ],
  "courses": [
        {"name": "course exp", "value": None},
        {"name": "cours edu", "value": None}],
  "tasks": [
        {"name": "task exp", "value": None},
        {"name": "task edu", "value": None}],
  "skills": [{"name":"manual skill", "type": "hard", "value": None},
            {"name":"Creative spirit", "type": "soft", "value": None}, 
            {"name":"Writing skills", "type": "hard", "value": None}, 
            {"name":"Communication", "type": "soft", "value": None},
            {"name": "skill edu", 'value': None, "type": "hard"},
            {"name": "skill exp", 'value': None, "type": "hard"}],
  "languages" : [{"name":"english", "value": None}],
  "interests": [{"name":"football", "value": None}],
  "tags":[{"name":"job_reference", "value": "external_id"}],
  "metadatas":[],
  "labels":[],
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
      'date_birth': '1990-08-09T00:00:00+0000',
      'email':'harry.potter@gmail.com',
      'phone':'0202',
      'gender': null,
      'urls': {
          'from_resume': [],
          'linkedin': '',
          'twitter': '',
          'facebook': '',
          'github': ''},
      'picture': null,
      'location':{'text': null},
      'summary': 'Brief summary'
  },
  'text': 'Harry Potter harry.potter@gmail.com 0202 Brief summary Mathematic Departement Developping Mathematicien University Description manual skill Creative spirit Writing skills Communication english football',
  'experiences': [{
      'date_start':  {'iso8601': '2018-01-01T00:00:00'},
      'date_end': {'iso8601': '2018-07-01T00:00:00'},
      'title': 'Lead',
      'company': 'Mathematic Departement',
      'description': 'Developping.',
      'location': {'text':'Paris', "lat":"lat", "lng": "lng"},
      'certifications': [{'name': 'certificate exp', 'value': null}],
      'courses': [{'name': 'cours exp', 'value': null}],
      'tasks': [{'name': 'tache exp', 'value': null}],
      'skills': [{'name': 'skill exp', 'value' : null, 'type' : 'hard'}]  
      }],
  'experiences_duration':5,
  'educations': [{
      'date_start': {'iso8601': '2016-01-01T00:00:00'},
      'date_end': {'iso8601': '2018-01-01T00:00:00'},
      'title': 'Mathematicien',
      'school': 'University',
      'description': 'Description',
      'location': {'text':'Scotland', 'lat':'lat', 'lng': 'lng'},
      'certifications': [{'name': 'certificate edu', 'value': null}],
      'courses': [{'name': 'cours edu', 'value': null}],
      'tasks': [{'name': 'tache edu', 'value': null}],
      'skills': [{'name': 'skill edu', 'value': null, 'type' : 'hard'}]
  }],
  'educations_duration':4,
  'certifications': [
            {'name': 'certificate exp', 'value': null},
            {'name': 'certificate edu', 'value': null}
            ],
  'courses': [
            {'name': 'cours exp', 'value': null},
            {'name': 'cours edu', 'value': null}],
  'tasks': [
            {'name': 'tache exp', 'value': null},
            {'name': 'tache edu', 'value': null}],
  'skills': [
            {'name': 'manual skill', 'type': 'hard', 'value': null},
            {'name': 'Creative spirit', "type": 'soft', 'value': null}, 
            {'name': 'Writing skills', "type": 'hard', 'value': null}, 
            {'name': 'Communication', 'type': 'soft', "value": null},
            {'name': 'skill edu', 'value': null, 'type': "hard"}
            {'name': 'skill exp', 'value': null, 'type': "hard"}],
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
