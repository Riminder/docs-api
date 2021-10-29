---
description: This endpoint allows you to retrieve a board info given a key.
---

# GET: /board

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/board" method="get" summary="Source" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email
{% endswagger-parameter %}

{% swagger-parameter in="query" name="key" type="string" %}
Board key
{% endswagger-parameter %}

{% swagger-response status="200" description="Board's info successfully retrieved." %}
```bash
{
    "code": 200,
    "message": "Board info",
    "data": {
        "id": 66,
        "key": "a9f42c53255d3774a0b997849ea1d52cc3192f4d",
        "name": "hiring campain",
        "description": "archive",
        "type": "api",
        "subtype": "python",
        "status": true,
        "archive": null,
        "members": [
            "alaeddine.chhima@riminder.net"
        ],
        "user": {
            "id": 221,
            "email": "alaeddine.chhima@riminder.net",
            "pseudo": null,
            "firstName": null,
            "lastName": null,
            "avatarUrl": "/images/user.png",
            "locale": "english",
            "position": null,
            "phone": null
        },
        "mapping_scoring": [],
        "mapping_reasoning": [],
        "updated_at": "2020-08-31T09:47:40+0000",
        "created_at": "2020-08-31T09:46:07+0000"
    }
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Coulf not find a board matching this query" %}
```bash
{
    "code": 400,
    "message": "Invalid board fields"
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Invalid secret key or unauthorized access" %}
```bash
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxxx "
}

OR

{
    "code": 401,
    "message": "Unauthorized Access to board key: xxxxxx"
}
```
{% endswagger-response %}
{% endswagger %}

## Example

{% tabs %}
{% tab title="Python" %}
```python
from hrflow import Hrflow

client = Hrflow(api_secret: "Your API Key", api_user: "Your API user email")

client.board.get(key="board_key")
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';
const client = new Hrflow({ 
    api_secret: 'Your API Key',
    api_user: 'Your API user email'
});

client.board.get('board_key').then(response => {
    console.log(response);
    // ...
});
```
{% endtab %}
{% endtabs %}
