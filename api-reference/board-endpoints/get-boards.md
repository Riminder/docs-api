---
description: This endpoint allows you to fetch boards from your workspace.
---

# GET: /boards

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/boards" method="get" summary="Boards" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" %}
Filter by board's name
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="string" %}
API page offset, default value is 

**1**
{% endswagger-parameter %}

{% swagger-parameter in="query" name="limit" type="integer" %}
Max response size, default value is 

**30**
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sort_by" type="string" %}
Sort by (ie. date, job), default value is 

**date.**
{% endswagger-parameter %}

{% swagger-parameter in="query" name="order_by" type="string" %}
Order by (ie asc, desc), default value is 

**desc**
{% endswagger-parameter %}

{% swagger-response status="200" description="Boards successfully retrieved." %}
```bash
{
    "code": 200,
    "message": "Board list",
    "meta": {
        "page": 1,
        "maxPage": 2,
        "count": 3,
        "total": 4
    },
    "data": [
        {
            "id": 66,
            "key": "a9f42c53255d3774a0b997849ea1d52cc3192f4d",
            "name": "hiring campaign ",
            "description": "archive ",
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
            "created_at": "2020-08-31T09:46:07+0000",
            "stats": {
                "size": "0"
            }
        },
        {
            "id": 65,
            "key": "8f10a8bc9279ab8cfc68ce60c9650e3b344fc1f0",
            "name": "folder",
            "description": "test",
            "type": "folder",
            "subtype": "folder",
            "status": true,
            "archive": null,
            "members": [
                "thomas.zhu@riminder.net"
            ],
            "user": {
                "id": 219,
                "email": "thomas.zhu@riminder.net",
                "pseudo": "Thomas",
                "firstName": "Thomas",
                "lastName": "ZHU",
                "avatarUrl": "/images/user.png",
                "locale": "english",
                "position": "Dealer",
                "phone": null
            },
            "mapping_scoring": [],
            "mapping_reasoning": [],
            "updated_at": "2020-08-25T10:19:08+0000",
            "created_at": "2020-08-25T10:19:08+0000",
            "stats": {
                "size": "1"
            }
        },
        {
            "id": 42,
            "key": "017f8c538b1d0021a53b4225dfa62a855871a19a",
            "name": "folder",
            "description": "test folder",
            "type": "folder",
            "subtype": "folder",
            "status": true,
            "archive": null,
            "members": [
                "mohamed.benqassmi@riminder.net",
                "cedric.defaut@riminder.net",
                "mouhidine.seiv@riminder.net",
                "thomas.zhu@riminder.net",
                "moustapha.ebnou@riminder.net"
            ],
            "user": {
                "id": 6,
                "email": "mohamed.nouayti@riminder.net",
                "pseudo": "mnouayti",
                "firstName": "Mohammed",
                "lastName": "NOUAYTI",
                "avatarUrl": "/images/user.png",
                "locale": "english",
                "position": "Lead Software Engineer",
                "phone": null
            },
            "mapping_scoring": [],
            "mapping_reasoning": [],
            "updated_at": "2020-07-02T15:41:19+0000",
            "created_at": "2020-07-02T15:26:52+0000",
            "stats": {
                "size": "13"
            }
        }
    ]
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Invalid secret key: xxxx" %}
```bash
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

client = Hrflow(api_secret: "Your API Key", api_user: "Your API user email")

client.board.list(name='compaign', page=1, limit=1, sort_by='date', order_by'asc')
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
  name: 'compaign',
  page: 1,
  limit: 10,
  sort_by: 'date',
  order_by: 'asc',
};
client.board.list(params).then(response => {
    console.log(response);
    // ...
});
```
{% endtab %}
{% endtabs %}
