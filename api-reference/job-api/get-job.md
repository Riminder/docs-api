---
description: Retrieve Job
---

# \[GET\] /job/indexing

{% hint style="info" %}
This endpoint requires at least job\_key and board\_key.
{% endhint %}

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/job/indexing" %}
{% api-method-summary %}
Get Job
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get a job.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="job\_key" type="string" required=true %}
Job's key.
{% endapi-method-parameter %}

{% api-method-parameter name="board\_key" type="string" required=true %}
Board's key
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



