---
description: >-
  Webhook Events represent all notification's king that will be sent to your
  account
---

# Webhook Events

## FORMAT

The webhook posts data to the URL you provided in the configuration. The body is encoded in JSON, which is indicated by the application/json content-type, with UTF-8 encoding \(as stated in RFC 4627 \([http://www.ietf.org/rfc/rfc4627.txt](http://www.ietf.org/rfc/rfc4627.txt)\).

## EVENTS TYPES

HrFlow  can send different events types to your application. Each call to the webhook URL will send an array of payloads.

| PAYLOAD | EVENT | STATUS | TYPE | DESCRIPTION | VOLUME |
| :--- | :--- | :--- | :--- | :--- | :--- |
| profile | parsing | `success` or `error` | `profile.parsing.success` or `profile.parsing.error` | Notification of the profile parsing status. | High volume |
| profile | embedding | `success` or `error` | `profile.embedding.success` or `profile.embedding.error` | Notification of the profile embedding status. | High volume |
| job | parsing | `success` or `error` | `job.parsing.success` or `job.parsing.error` | Notification of the job parsing status. | High volume |
| job | embedding | `success` or `error` | `job.embedding.success` or `job.embedding.error` | Notification of the job embedding status. | High volume |
| action | stage | `success` or `error` | `action.stage.success` or `action.stage.error` | Notification of action stage status. | Low volume |

## Handling an event

Handling an event is very simple. You can specify callback function to handle every event incoming on your webhooks endpoint. Each event must have its own handling function.

**Requirements**

* The request header
* The API secret key
* The webhook secret key
* An endpoint receiving post requests

Examples :

{% tabs %}
{% tab title="Python" %}
```python
import hrflow as hf 

def func_callback(event_name, webhook_data):
  print("{} {}".format(event_name, webhook_data)

client = hf.Client(api_secret='api_secret', webhook_secret='webhook_key')

# Set an handler for webhook event.
callback = func_callback
resp = client.webhooks.setHandler('profile.parsing.success', callback)
        
# Get the header of the request sent by the webhook.
rcvheaders = function_that_get_webhook_request_headers()
        
# Handle the webhook
client.webhooks.handle(request_headers=rcvheaders)
```
{% endtab %}
{% endtabs %}

