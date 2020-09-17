---
description: This endpoint allows you to generate text parsing from a full text input.
---

# POST : /document/parsing

{% api-method method="post" host="https://api.hrflow.ai" path="/v1/document/parsing" %}
{% api-method-summary %}
Post /document/parsing
{% endapi-method-summary %}

{% api-method-description %}
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

{% api-method-body-parameters %}
{% api-method-parameter name="text" type="string" required=true %}
Text to be parsed
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Parsing is succuessfully generated
{% endapi-method-response-example-description %}

```bash
{
    "code": 200,
    "message": "Parsing results",
    "data": {
        "ents": [
            {
                "end": 11,
                "label": "Person",
                "start": 0
            },
            {
                "end": 33,
                "label": "Job_title",
                "start": 17
            }
        ],
        "text": "Harry Potter is a Python Enginner"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Text can't be null.
{% endapi-method-response-example-description %}

```bash
{
    "code": 400,
    "message": "Bad request. Text cannot be null"
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
    "message": "Unauthorized. Invalid secret key: xxxx for permission: write"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="Python" %}
```python
from hrflow import Hrflow

client = Hrflow(api_secret="Your API Key", api_user="Your API user email")


response = client.document.parsing.post(text="Harry Potter is a Python Enginner")
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';
const client = new Hrflow({ 
    api_secret: 'Your API Key',
    api_user: 'Your API user email'
});

client.document.parsing.post("Harry Potter is a Python Enginner")
.then(response => {
    console.log(response);
    // ...
});

```
{% endtab %}
{% endtabs %}



