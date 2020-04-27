---
description: Retrieve source's information for a given source id
---

# \[GET\] /source

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/source" %}
{% api-method-summary %}
Source
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to retrieve given source's information.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="source\_id" type="string" required=true %}
Source id
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Source's info successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "code": 200,
    "message": "Source info",
    "data": {
        "source_id": "source_id",
        "name": "test",
        "type": "folder",
        "sub_type": "folder",
        "archive": false,
        "date_creation": {
            "date": "2020-01-21 12:59:38.000000",
            "timezone_type": 3,
            "timezone": "UTC"
        }
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a source matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "code": 400,
    "message": "Bad Request. Invalid source_id: xxxxx"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret key.
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
{% tab title="Bash" %}
```bash
$curl --url "https://api.hrflow.ai/source?source_id=source_id" --header "X-API-KEY: api_key"
```
{% endtab %}

{% tab title="PHP" %}
```php
$client->source->get('source_id');
```
{% endtab %}

{% tab title="Python" %}
```python
client.source.get(source_id="source_id")
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
// npm install --save hrflow

import Hrflow from 'hrflow';
const client = new Hrflow({API_Key: "Your API Key"});

client.source.get("source_id_here").then(response => {
    console.log(response);
    // ...
});

```
{% endtab %}
{% endtabs %}

