---
description: Retrieve all boards created by a team
---

# \[GET\] /boards

{% api-method method="get" host="https://api.hrflow.ai" path="/v1/boards" %}
{% api-method-summary %}
Boards
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get all sources created by your team.
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

{% api-method-query-parameters %}
{% api-method-parameter name="name" type="string" required=false %}
Filter by board's name
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="string" required=false %}
API page offset \(Default is 1\)
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
Max response size \(Default is 30\)
{% endapi-method-parameter %}

{% api-method-parameter name="sort\_by" type="string" %}
Sort by \(ie. date\)
{% endapi-method-parameter %}

{% api-method-parameter name="order\_by" type="string" %}
Order by \(ie asc, desc\)  
Default is desc
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{    "name": "Cake's name",    "recipe": "Cake's recipe name",    "cake": "Binary cake"}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{    "message": "Ain't no cake like that."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



