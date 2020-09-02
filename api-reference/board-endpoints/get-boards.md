---
description: Retrieve all boards from your workspace
---

# GET: /boards

{% api-method method="get" host="https://api.hrflow.ai" path="/v1/boards" %}
{% api-method-summary %}
Boards
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to fetch boards from your workspace.
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
{% api-method-parameter name="name" type="string" required=false %}
Filter by board's name
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="string" required=false %}
API page offset \(Default is 1\)
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
Max response size \(Default is 30\)
{% endapi-method-parameter %}

{% api-method-parameter name="sort\_by" type="string" %}
Sort by \(ie. date, job\)  
Default is date.
{% endapi-method-parameter %}

{% api-method-parameter name="order\_by" type="string" %}
Order by \(ie asc, desc\)  
Default is desc
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Boards successfully retrieved.
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret key: xxxx
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

{% tabs %}
{% tab title="Python" %}
```python
import hrflow as hf

client = hf.client(api_secret: "Your API Key", api_user: "Your API user email")

client.board.list(name='compaign', page=1, limit=1, sort_by='date', order_by'asc')
```
{% endtab %}
{% endtabs %}

