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
 Authentication token
{% endapi-method-parameter %}

{% api-method-parameter name="X-USER-EMAIL" type="string" required=true %}
 User's email
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="source\_key" type="string" required=true %}
Source key
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
        "key": "source_key",
        "name": "source_name",
        "type": "folder",
        "sub_type": "folder",
        "archive": null,
        "date_creation": "2020-05-26T01:47:03+0000"
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
    "message": "Bad Request. Invalid source_key: xxxxx"
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
require_once('vendor/autoload.php');

$client = new Hrflow\Client('your secert key');

$source_id = 'source_id' ;

$client->source->get($source_id) ;

```
{% endtab %}

{% tab title="Python" %}
```python
import hrflow as hf

client = hf.client(api_secret='your secret key')

client.source.get(source_id="source_id")
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
// npm install --save hrflow

import Hrflow from 'hrflow';
const client = new Hrflow({ 
    api_secret: "Your API Key",
    api_user: "Your API user email" 
});

client.source.get("source_id_here").then(response => {
    console.log(response);
    // ...
});

```
{% endtab %}
{% endtabs %}

