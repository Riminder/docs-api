---
description: Check webhook integration for given team account
---

# Authentication

{% api-method method="post" host="https://api.hrflow.ai/v1" path="/webhook/check " %}
{% api-method-summary %}
/webhook/check
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="url" type="string" required=false %}
Webhook callback url.
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=false %}
Webhook type.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Webhook successfully checked.
{% endapi-method-response-example-description %}

```javascript
{
    "code": 200,
    "message": "ok",
    "data": {
        "team_name": "stark",
        "webhook_id": "wid_6637839405e8b44e75b38e",
        "url": "https://webhook.site/79f29230-9346-44e9-997f-035365443a64",
        "type": "profile.parsing.success"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret token.
{% endapi-method-response-example-description %}

```java
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxxx "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

