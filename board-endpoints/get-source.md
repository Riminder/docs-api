---
description: Retrieve a board info
---

# GET: /board

{% api-method method="get" host="https://api.hrflow.ai" path="/v1/board" %}
{% api-method-summary %}
Source
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to retrieve a board info given a key.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token
{% endapi-method-parameter %}

{% api-method-parameter name="X-USER-EMAIL" type="string" required=true %}
User's email
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="key" type="string" required=true %}
Board key
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Board's info successfully retrieved.
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Coulf not find a board matching this query
{% endapi-method-response-example-description %}

```bash
{
    "code": 400,
    "message": "Invalid board fields"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret key
{% endapi-method-response-example-description %}

```bash
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



