---
description: Retrieve profile's attachments given profile key and source key.
---

# \[GET\] /profile/indexing/attachments

{% hint style="info" %}
This endpoint requires either profile key or profile reference or profile email.
{% endhint %}

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/profile/attachments" %}
{% api-method-summary %}
Get /profile/attachments
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get profile's attachments.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token.
{% endapi-method-parameter %}

{% api-method-parameter name="X-USER-EMAIL" type="string" required=true %}
User's email
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="source\_key" type="string" required=true %}
Source key.
{% endapi-method-parameter %}

{% api-method-parameter name="key" type="string" required=true %}
Profile key.
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" %}
Profile's reference.
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" %}
Profile's email.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Attachments successfully retrieved.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 200,
    "message": "Profile attachment list",
    "data": [
        {
            "type": "resume",
            "alt": "id",
            "file_name": "resume.pdf",
            "original_file_name": "resume",
            "file_size": 194094,
            "extension": "pdf",
            "public_url": "http://www.hrflow.ai/profile/attachment?key=key_value&type=resume",
            "timestamp": 1579252136
        },
        {
            "type": "original",
            "alt": "id",
            "file_name": "original.pdf",
            "original_file_name": "original",
            "file_size": 137690,
            "extension": "pdf",
            "public_url": "http://www.hrflow.ai/profile/attachment?key=key_value=&type=original",
            "timestamp": 1579252136
        }
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a profile matching this query.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 400,
    "message": "Invalid profile array"
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

### Example

{% tabs %}
{% tab title="PHP" %}
```php
require_once('vendor/autoload.php');

$client = new Hrflow\Client('your secret key');

$source_id         = 'source_id' ;
$profile_id        = 'profile_id';
$profile_reference = 'profile_reference'; // optional
$profile_email     = 'profile_email'; // optional

$client->profile->attachment->list($source_id, $profile_id, $profile_reference, $profile_email);
```
{% endtab %}

{% tab title="Python" %}
```python
import hrflow as hf

client = hf.client(api_secret='your api secret')

client.profile.attachment.list(source_id="source_id",
                               profile_id="profile_id",
                               profile_reference='profile ref',
                               profile_email='profile@email.ai'))import Hrflow from 'hrflow';
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';

const client = new Hrflow({ 
    api_secret: "Your API Key",
    api_user: "Your API user email" 
});

const params = {
    source_key: "source_key",
    key: "profile_key",
    // Or
    reference: "reference"
    email: 'example@example.com',
}

client.profile.attachments.list(params);
```
{% endtab %}
{% endtabs %}

