---
description: This endpoint allows you to get the Profile's attachment.
---

# GET: /profile/indexing/attachment

{% hint style="info" %}
One of key , reference or email parameters should be provided to identify the profile.
{% endhint %}

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/profile/indexing/attachments" method="get" summary="Get /profile/indexing/attachments" %}
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

{% swagger-response status="200" description="Parsing successfully retrieved." %}
```scheme
{'code': 200,
 'data': [{'alt': 'alt_key',
           'created_at': '2020-09-11T09:58:32+0000',
           'extension': '.pdf',
           'file_name': 'resume',
           'file_size': 528305,
           'original_file_name': 'resume',
           'public_url': 'public_url_resume',
           'type': 'resume',
           'updated_at': '2020-09-11T09:58:32+0000'},
          {'alt': 'alt_key',
           'created_at': '2020-09-11T09:58:32+0000',
           'extension': '.pdf',
           'file_name': 'original',
           'file_size': 537789,
           'original_file_name': 'original',
           'public_url': 'public_url_original',
           'type': 'original',
           'updated_at': '2020-09-11T09:58:32+0000'}],
 'message': 'Profile attachment list'}
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
    "message": "Unauthorized. Invalid secret key: xxxxx "
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

 client.profile.attachment.list(source_key="source_key",
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

client.profile.attachment.list('source_key', {
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
