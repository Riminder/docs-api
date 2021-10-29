---
description: Check your webhook credentials
---

# Webhook Authentication

{% swagger baseUrl="https://api.hrflow.ai/v1" path="/webhook/check " method="post" summary="/webhook/check" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" type="string" %}
Webhook callback url.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="string" %}
Webhook type.
{% endswagger-parameter %}

{% swagger-response status="200" description="Webhook successfully checked." %}
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
{% endswagger-response %}

{% swagger-response status="401" description="Invalid secret token." %}
```java
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxxx "
}
```
{% endswagger-response %}
{% endswagger %}

### Example

{% tabs %}
{% tab title="PHP" %}
```php
require_once('vendor/autoload.php');

$client = new Hrflow\Client('your secret key');

$data = [
    'url'  => 'webhook url',
    'type' => 'profile.parsing.success'
];

$client->webhooks->check($data) ;
```
{% endtab %}

{% tab title="Python" %}
```python
  client.webhooks.check()
```
{% endtab %}
{% endtabs %}
