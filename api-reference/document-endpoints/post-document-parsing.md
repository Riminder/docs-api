---
description: This endpoint allows you to generate text parsing from a full text input.
---

# POST : /document/parsing

{% swagger baseUrl="https://api.hrflow.ai" path="/v1/document/parsing" method="post" summary="Post /document/parsing" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-USER-EMAIL" type="string" %}
User's email.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="text" type="string" %}
Text to be parsed
{% endswagger-parameter %}

{% swagger-response status="200" description="Parsing is succuessfully generated" %}
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
{% endswagger-response %}

{% swagger-response status="400" description="Text can't be null." %}
```bash
{
    "code": 400,
    "message": "Bad request. Text cannot be null"
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Invalid secret key" %}
```bash
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxx for permission: write"
}
```
{% endswagger-response %}
{% endswagger %}

As output , this API sends you back all parsed entities.

There are 17 labels :

* FirstName
* LastName
* Date
* Duration
* Location
* Company
* JobTitle
* Task
* School&#x20;
* EduTitle
* Course
* Skill
* Certification
* Language
* Interest
* Email
* Phone

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
