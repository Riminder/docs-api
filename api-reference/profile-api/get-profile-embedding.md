---
description: Retrieve profile's embedding given profile id and source id.
---

# \[GET\] /profile/embedding

{% hint style="info" %}
This endpoint requires either profile\_id or profile\_reference or profile\_email.
{% endhint %}

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/profile/embedding" %}
{% api-method-summary %}
Get /profile/embedding
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="source\_id" type="string" required=true %}
Source id
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_id" type="string" required=true %}
Profile id
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_reference" type="string" required=false %}
Profile's reference
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_email" type="string" required=false %}
Profile's email
{% endapi-method-parameter %}

{% api-method-parameter name="fields" type="object" required=false %}
\(ie {"profile":1, "skills":1, "experiences": \[0\]}\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Embeddings successfully retriveied
{% endapi-method-response-example-description %}

```javascript
{
    "code": 200,
    "message": "Profile embedding",
    "data": {
        "profile": "link to Profile vector",
        "skills": "link to Skills vector",
        "experiences": [
            "link to Exp vector"
        ]
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a profile matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "code": 400,
    "message": "Invalid profile array"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret key
{% endapi-method-response-example-description %}

```javascript
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
$client->profile->embedding->get($source_id, new ProfileId("profile_id"), 
                                ['skills'=>1, 'profile'=>1, 'educations'=>[0]]);
```
{% endtab %}

{% tab title="Python" %}
```python
client.profile.embedding.get(source_id='source_id',
                             profile_id='profile_id',
                             fields={'profile': 1, 'skills':1, 'educations':[0]})
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
// npm install --save hrflow


import Hrflow from 'hrflow';
const hrflow = new Hrflow({API_Key: "Your API Key"});

const data = {
    source_id: "source_id",
    profile_id: "id",
    // Or
    profile_reference: "reference"
}

hrflow.profile.embedding.get(data);
```
{% endtab %}
{% endtabs %}

