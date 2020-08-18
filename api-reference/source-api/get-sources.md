---
description: Retrieve all sources created by a team
---

# \[GET\] /sources

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/sources" %}
{% api-method-summary %}
Sources
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get all sources created by your team.
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
{% api-method-parameter name="name" type="string" required=false %}
Filter by source's name.
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="integer" required=false %}
API  page offset.  
Deafult is 1
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
Max response size.  
Default  is 30
{% endapi-method-parameter %}

{% api-method-parameter name="sort\_by" type="string" required=false %}
Sort by \(ie. date, profile\)  
Default is Date
{% endapi-method-parameter %}

{% api-method-parameter name="order\_by" type="string" required=false %}
Order by \(.ie asc, desc\)  
Default is desc
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Source list successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "code": 200,
    "page": 1,
    "maxPage": 10,
    "count": 30,
    "total": 273,
    "message": "Source list",
    "data": [
        {
            "source_id": "source_exemple_id",
            "name": "python",
            "type": "api",
            "sub_type": "api",
            "archive": false,
            "date_creation": {
                "date": "2020-03-03 23:18:16.000000",
                "timezone_type": 3,
                "timezone": "UTC"
            },
            "stats": {
                "total_profiles": "n"
            }
        },
        .
        .
        .
        .
        ]
    }
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

## Example

{% tabs %}
{% tab title="Bash" %}
```bash
$curl --url "https://api.hrflow.ai/sources?name=python&page=2&limit=5&sort_by=date&order_by=asc" --header "X-API-KEY: api_key"
```
{% endtab %}

{% tab title="PHP" %}
```php
require_once('vendor/autoload.php');

$client = new Hrflow\Client('your secret key');

$params = [
    'name'     => 'cvbot',
    'page'     => 1,
    'limit'    => 10,
    'sort_by'  => 'date',
    'order_by' => 'asc',
];

$resp = $client->source->list($params) ;
```
{% endtab %}

{% tab title="Python" %}
```python
imoort hrflow as hf

client = hf.client(api_secret: "Your API Key", api_user: "Your API user email")

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



