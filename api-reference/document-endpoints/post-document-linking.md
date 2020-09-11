# POST : /document/linking

{% api-method method="post" host="https://api.hrflow.ai" path="/v1/document/linking" %}
{% api-method-summary %}
Post /document/linking
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to generate the linking output from a full text input.
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
A text to calculate most similar token
{% endapi-method-parameter %}

{% api-method-parameter name="top\_n" type="string" required=false %}
The n most similar word to a given text   
\( Default value is 5\)
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Top n most similar word for a given text retreived successfully
{% endapi-method-response-example-description %}

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

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Text can't be null
{% endapi-method-response-example-description %}

```bash
{
    "code": 400,
    "message": "Bad request. Text cannot be null"
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


response = client.document.linking.post(text="python", top_n=20)
```
{% endtab %}
{% endtabs %}

