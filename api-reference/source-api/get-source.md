---
description: This endpoint allows you to retrieve a source info given a key.
---

# GET: /source

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/source" method="get" summary="Source" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email
{% endswagger-parameter %}

{% swagger-parameter in="query" name="key" type="string" %}
Source key
{% endswagger-parameter %}

{% swagger-response status="200" description="Source's info successfully retrieved." %}
```javascript
    "code": 200,
    "message": "Source info",
    "data": {
        "id": 1166,
        "key": "91456df437fbd49a566adc5e0b0b33d13b115d06",
        "name": "folder demo",
        "description": null,
        "type": "folder",
        "subtype": "folder",
        "private": true,
        "status": true,
        "archive": null,
        "members": [
            "mohamed.benqassmi@riminder.net"
        ],
        "notification": false,
        "consent": false,
        "consent_url": null,
        "user": {
            "id": 16,
            "email": "mohamed.benqassmi@riminder.net",
            "pseudo": "medbenqa",
            "firstName": null,
            "lastName": null,
            "avatarUrl": "/images/user.png",
            "locale": "english",
            "position": null,
            "phone": null
        },
        "updated_at": "2020-09-01T17:51:36+0000",
        "created_at": "2020-09-01T17:51:36+0000"
    }
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Could not find a source matching this query." %}
```javascript
{
    "code": 400,
    "message": "Invalid source fields"
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Invalid secret key or unauthorized access." %}
```javascript
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxxx "
}

OR

{
    "code": 401,
    "message": "Unauthorized Access to source key: xxxxxx"
}
```
{% endswagger-response %}
{% endswagger %}

## Example

{% tabs %}
{% tab title="Bash" %}
```bash
$curl --url "https://api.hrflow.ai/source?source_id=source_id" --header "X-API-KEY: api_key"
```
{% endtab %}

{% tab title="Python" %}
```python
from hrflow import Hrflow

client = Hrflow(api_secret: "Your API Key", api_user: "Your API user email")

client.source.get(key="source_key")
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
// npm install --save hrflow

import Hrflow from 'hrflow';
const client = new Hrflow({ 
    api_secret: 'Your API Key',
    api_user: 'Your API user email'
});

client.source.get('source_key').then(response => {
    console.log(response);
    // ...
});
```
{% endtab %}
{% endtabs %}
