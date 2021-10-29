---
description: This endpoint allows you to get the Parsing object.
---

# GET: /profile/parsing

{% hint style="info" %}
One of key , reference or email parameters should be provided to identify the profile.
{% endhint %}

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/profile/parsing" method="get" summary="Get /profile/parsing" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email.
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

{% swagger-response status="200" description="Parsing object successfully retrieved." %}
```scheme
{
    "code": 200,
    "message": "Profile parsing",
    "data": {
      'content_uid': 'content_uid', 
      'key': 'profile_key',
      'file_name': 'filename.pdf',
      'file_size': null, 
      'persons': [{'full_name': 'Harry Potter', 
                   'first_name': 'Harry',
                   'last_name': 'Potter'}],
      'emails': ['harry.potter@gmail.com'],
      'phones': ['0202'],
      'date_birth': {
            'iso8601': '1990-08-09T00:00:00',
            'text': '08/09/1990",
            'timestamp': 650160000
        },
      'location': {
           'text': '803 Green Lane London N07 8MA',
           'lat': 51.581551, 
           'lng': -0.099649, 
           'geojson': {
              'house': null, 
              'category': null, 
              'near': null, 
              'house_number': 803, 
              'road': 'Green Lane', 
              'unit': null, 
              'level': null, 
              'staircase': null, 
              'entrance': null, 
              'po_box': null, 
              'postcode': null, 
              'suburb': null, 
              'city_district': null, 
              'city': 'London', 
              'island': null, 
              'state_district': null, 
              'state': null, 
              'country_region': null, 
              'country': 'UK', 
              'world_region': null}}, 
     'images': null, 
     'picture': 'https://myPicture.com',
     'urls': [
              {'type': 'from_resume', 'url': []}, 
              {'type': 'linkedin', 'url': null}, 
              {'type': 'twitter', 'url': null}, 
              {'type': 'facebook', 'url': null}, 
              {'type': 'github', 'url': null}],
     'gender': 'male',
     'driving_license': null, 
     'summary': 'Brief summary', 
     'text': 'Profile s text' ,
     'text_language': 'en'
     'educations': [
                    {'content_uid': 'content_uid',
                     'title': 'Mathematicien'                     
                     'school': 'University',
                     'description': 'Education description',
                     'date_start': {
                                    'iso8601': '2016-01-01T00:00:00',
                                    'text': '2016-01-01',
                                    'timestamp': 1451602800},
                     'date_end': {
                                  'iso8601': '2018-01-01T00:00:00', 
                                  'text': '2018-01-01', 
                                  'timestamp': 1514761200},
                     'location': {'geojson': {'category': null,
                                          'city': null,
                                          'city_district': null,
                                          'country': null,
                                          'country_region': null,
                                          'entrance': null,
                                          'house': null,
                                          'house_number': null,
                                          'island': null,
                                          'level': null,
                                          'near': null,
                                          'po_box': null,
                                          'postcode': null,
                                          'road': null,
                                          'staircase': null,
                                          'state': null,
                                          'state_district': null,
                                          'suburb': null,
                                          'unit': null,
                                          'world_region': null},
                              'lat': null,
                              'lng': null,
                              'text': null},
                     'certifications': [{'name': 'certificate edu', 'value': null}],
                     'courses': [{'name': 'course edu', 'value': null}],
                     'tasks': [{'name': 'task edu', 'value': null}]
                     'skills': [{'name': 'skill edu', 'type': 'hard', 'value': null}]
                              }],
     'educations_duration': 2,
     'experiences': [
                     {'content_uid': 'content_uid',
                      'title': 'Data scientist'
                      'company': 'Mathematic Departement',
                      'description': 'Experience s description',
                      'date_start': {'iso8601': '2018-01-01T00:00:00',
                                     'text': '2018-01-01',
                                     'timestamp': 1467324000},
                      'date_end': {'iso8601': '2018-07-01T00:00:00',
                                   'text': '2018-07-01',
                                   'timestamp': 1530396000},
                      'location': {'geojson': {'category': null,
                                               'city': null,
                                               'city_district': null,
                                               'country': null,
                                               'country_region': null,
                                               'entrance': null,
                                               'house': null,
                                               'house_number': null,
                                               'island': null,
                                               'level': null,
                                               'near': null,
                                               'po_box': null,
                                               'postcode': null,
                                               'road': null,
                                               'staircase': null,
                                               'state': null,
                                               'state_district': null,
                                               'suburb': null,
                                               'unit': null,
                                               'world_region': null},
                                   'lat': null,
                                   'lng': null,
                                   'text': null},
                        'certifications': [{'name': 'certificate exp', 'value': null}],
                        'courses': [{'name': 'course exp', 'value': null}],
                        'tasks': [{'name': 'task exp', 'value': null}]
                        'skills': [{'name': 'skill exp', 'type': 'hard', 'value': null}]
                        }],
     'experiences_duration': 0.7,
     'skills': [{'name':'manual skill', 'type': 'hard', 'value': null},
                {'name':'Creative spirit', 'type': 'soft','value': null}, 
                {'name':'Writing skills', 'type': 'hard','value': null}, 
                {'name':'Communication', 'type': 'soft','value': null},
                {'name':'skill edu', 'type': 'hard','value': null},
                {'name':'skill edu', 'type': 'hard','value': null}],
     'courses': [{'name': 'course exp', 'value': null},
                 {'name': 'course edu', 'value': null}],
     'certifications': [{'name': 'certificate exp', 'value': null},
                        {'name': 'certificate edu', 'value': null}],
     'tasks': [{'name': 'task exp', 'value': null},
               {'name': 'task edu', 'value': null}]
     'languages': [{'name':'english', 'value': null}],
     'interests': [{'name':'football', 'value': null}],
     'total_pages': 1,
     'processed_pages': 1
    }
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Could not find a source matching this query." %}
```scheme
{
    "code": 400,
    "message": "Invalid source fields"
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Invalid secret key." %}
```scheme
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxxx for permission: all"
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

client.profile.parsing.get(source_key="source_key",
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
    api_user: 'Your API user email',
});

client.profile.parsing.get('source_key', {
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
