---
description: This endpoint allows you to fetch sources from your workspace.
---

# GET: /sources

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/sources" method="get" summary="Sources" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" %}
Filter by source's name.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="integer" %}
API page offset, default value is 

**1**
{% endswagger-parameter %}

{% swagger-parameter in="query" name="limit" type="integer" %}
Max response size, default value is 

**30**
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sort_by" type="string" %}
Sort by (ie. date, profile), default value is 

**date**
{% endswagger-parameter %}

{% swagger-parameter in="query" name="order_by" type="string" %}
Order by (.ie asc, desc), default value is 

**desc**
{% endswagger-parameter %}

{% swagger-response status="200" description="Source list successfully retrieved." %}
```javascript
{
    "code": 200,
    "message": "Source list",
    "meta": {
        "page": 1,
        "maxPage": 11,
        "count": 3,
        "total": 33
    },
    "data": [
        {
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
            "created_at": "2020-09-01T17:51:36+0000",
            "stats": {
                "size": "1"
            }
        },
        {
            "id": 1165,
            "key": "c5db72c0a4de151f05c10e80560668f872e84322",
            "name": "cvbot demo",
            "description": null,
            "type": "cvbot",
            "subtype": "cvbot",
            "private": false,
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
            "updated_at": "2020-09-01T13:38:56+0000",
            "created_at": "2020-09-01T13:38:56+0000",
            "stats": {
                "size": "0"
            }
        },
        {
            "id": 1164,
            "key": "b707a108bc0d90004be2f91ec4ae9260e1c942d4",
            "name": "http_api demo",
            "description": null,
            "type": "api",
            "subtype": "http_api",
            "private": false,
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
            "updated_at": "2020-09-01T12:01:04+0000",
            "created_at": "2020-09-01T12:01:04+0000",
            "stats": {
                "size": "0"
            }
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Invalid secret key: xxxx" %}
```javascript
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxxx for permission: all"
}
```
{% endswagger-response %}
{% endswagger %}

## Example

{% tabs %}
{% tab title="Bash" %}
```bash
$curl --url "https://api.hrflow.ai/sources?name=python&page=2&limit=5&sort_by=date&order_by=asc" --header "X-API-KEY: api_key"
```
{% endtab %}

{% tab title="Python" %}
```python
from hrflow import Hrflow

client = Hrflow(api_secret: "Your API Key", api_user: "Your API user email")

client.source.list(name='cvbot', page=1, limit=1, sort_by='date', order_by'asc')
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';
const client = new Hrflow({ 
    api_secret: 'Your API Key',
    api_user: 'Your API user email' 
});

const params = {
  name: 'cvbot',
  page: 1,
  limit: 10,
  sort_by: 'date',
  order_by: 'asc',
};
client.source.list(params).then(response => {
    console.log(response);
    // ...
});
```
{% endtab %}
{% endtabs %}
