---
description: This endpoint allows you to get the Profile's attachment.
---

# GET: /profile/indexing/attachment

{% hint style="info" %}
One of key , reference or email parameters should be provided to identify the profile.
{% endhint %}

{% api-method method="get" host="https://api.hrflow.ai" path="/v1/profile/indexing/attachments" %}
{% api-method-summary %}
Get /profile/indexing/attachments
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
Parsing successfully retrieved.
{% endapi-method-response-example-description %}

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
    "message": "Unauthorized. Invalid secret key: xxxxx "
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

