---
description: >-
  This endpoint allows you to generate the linking output from a full text
  input.
---

# POST : /document/linking

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/document/linking" method="post" summary="Post /document/linking" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="text" type="string" %}
A text to calculate most similar token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="top_n" type="string" %}
The n most similar word to a given text

\


( Default value is 5)
{% endswagger-parameter %}

{% swagger-response status="200" description="Top n most similar word for a given text retreived successfully" %}
```bash
{
    "code": 200,
    "message": "Linking results",
    "data": [
        [
            "perl",
            0.86659765243530273
        ],
        [
            "bash",
            0.83746224641799927
        ],
        [
            "django",
            0.82120096683502197
        ],
        [
            "java",
            0.82105296850204468
        ]
    ]
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

{% swagger-response status="404" description="Text can't be null" %}
```bash
{
    "code": 400,
    "message": "Bad request. Text cannot be null"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Python" %}
```python
from hrflow import Hrflow

client = Hrflow(api_secret="Your API Key", api_user="Your API user email")


response = client.document.linking.post(text="python", top_n=20)
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
const client = new Hrflow({ 
    api_secret: 'Your API Key',
    api_user: 'Your API user email'
});

client.document.linking.post("python", 20).then(response => {
    console.log(response);
    // ...
});
```
{% endtab %}
{% endtabs %}
