---
description: >-
  This endpoint allows you to generate the revealing output from a full text
  input.
---

# POST: /document/revealing

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/document/revealing" method="post" summary="Post /document/revealing" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email
{% endswagger-parameter %}

{% swagger-parameter in="body" name="text" type="string" %}
Text to reveal
{% endswagger-parameter %}

{% swagger-response status="200" description="Revealing successfully generated." %}
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
{% endswagger-response %}

{% swagger-response status="400" description="Text can't be null." %}
```bash
{
    "code": 400,
    "message": "Bad request. Text cannot be null"
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Invalid secret key." %}
```bash
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxx for permission: write"
}
```
{% endswagger-response %}
{% endswagger %}

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
