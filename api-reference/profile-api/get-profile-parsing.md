---
description: This endpoint allows you to get the Parsing object.
---

# GET: /profile/parsing

{% hint style="info" %}
One of key , reference or email parameters should be provided to identify the profile.
{% endhint %}

{% api-method method="get" host="https://api.hrflow.ai" path="/v1/profile/parsing" %}
{% api-method-summary %}
Get /profile/parsing
{% endapi-method-summary %}

{% api-method-description %}

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
{% api-method-parameter name="source\_key" type="string" required=true %}
The source unique identifier
{% endapi-method-parameter %}

{% api-method-parameter name="key" type="string" required=false %}
The profile unique identifier
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=false %}
The profile's reference
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=false %}
The profile's email
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Parsing object successfully retrieved.
{% endapi-method-response-example-description %}

```scheme
{
      'content_uid': 'content_uid', 
      'key': 'profile_key',
      'file_name': 'filename.pdf',
      'file_size': null, 
      'persons': [{'full_name': 'Harry Potter', 
                   'first_name': 'Harry',
                   'last_name': 'Potter'}],
      'emails': ['harry.potter@gmail.com'],
      'phones': ['0202'],
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
     'picture': 'https://riminder-documents-eu-2019-12.s3-eu-west-1.amazonaws.com/picture.png',
     'urls': [
              {'type': 'from_resume', 'url': []}, 
              {'type': 'linkedin', 'url': null}, 
              {'type': 'twitter', 'url': null}, 
              {'type': 'facebook', 'url': null}, 
              {'type': 'github', 'url': null}],
     'gender': 'male',
     'driving_licence': null, 
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
                              'text': null}}
               ],
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
                                   'text': null}
                        }],
     'experiences_duration': 0.7,
     'skills': [{'name':'manual skill', 'type': 'hard', 'value': null},
                {'name':'Creative spirit', 'type': 'soft','value': null}, 
                {'name':'Writing skills', 'type': 'hard','value': null}, 
                {'name':'Communication', 'type': 'soft','value': null}],
     'languages': [{'name':'english', 'value': null}],
     'interests': [{'name':'football', 'value': null}]
 }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a source matching this query.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 400,
    "message": "Invalid source fields"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret key.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxxx for permission: all"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

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

