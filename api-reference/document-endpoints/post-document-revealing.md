---
description: >-
  This endpoint allows you to generate the revealing output from a full text
  input.
---

# POST: /document/revealing

{% api-method method="post" host="https://api.hrflow.ai" path="/v1/document/revealing" %}
{% api-method-summary %}
Post /document/revealing
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
User's email
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="text" type="string" required=true %}
Text to reveal
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Revealing successfully generated.
{% endapi-method-response-example-description %}

```bash
{
    "code": 200,
    "message": "Revealing results",
    "data": [
        [
            "Financial Reporting",
            0.41042819600000002
        ],
        [
            "Microsoft Excel",
            0.401153237
        ],
        [
            "Customer Service",
            0.32542374699999999
        ],
        [
            "Microsoft Office",
            0.32138148
        ]....
    ]
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
Invalid secret key.
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

{% hint style="info" %}
Max limit token is 512, if for a given text, this limit is exceeded, we will consider the first 512 tokens.
{% endhint %}

{% tabs %}
{% tab title="Python" %}
```python
from hrflow import Hrflow

client = Hrflow(api_secret="Your API Key", api_user="Your API user email")


response = client.document.revealing.post(text="hello")
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import Hrflow from 'hrflow';
const client = new Hrflow({ 
    api_secret: 'Your API Key',
    api_user: 'Your API user email'
});

client.document.revealing.post("text").then(response => {
    console.log(response);
    // ...
});
```
{% endtab %}
{% endtabs %}

