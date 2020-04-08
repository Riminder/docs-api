# GET /profile/metadatas

{% hint style="info" %}
This endpoint requires either profile\_id or profile\_reference or profile\_email.
{% endhint %}

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/profile/metadatas" %}
{% api-method-summary %}
Get /profile/metadatas
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="source\_id" type="string" required=true %}
Source id
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_id" type="string" required=true %}
Profile id
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_reference" type="string" required=false %}
Profile's reference
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_email" type="string" required=false %}
Profile's email
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Metadatas successfully retrieved
{% endapi-method-response-example-description %}

```javascript
{
    "code": 200,
    "message": "Profile metadatas",
    "data": [
        {
            "name": "email",
            "value": "test@hrflow.ai"
        }
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a profile matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "code": 400,
    "message": "Invalid profile array"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret token.
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

