---
description: Setting up your webhook integration.
---

# Webhook Configuration

## Signature

When WEBHOOK integration sends an event notification, a HTTP POST request is made to your specified **WEBHOOK URL**. This POST request will contain some parameters, including the **HTTP-HRFLOW-SIGNATURE** header parameter which you can use for authorization.

The HTTP-HRFLOW-SIGNATURE is base64url encoded and signed with an HMAC version of your WEBHOOK SECRET KEY with the SHA-256 digest.

What this means is that when it is POSTed to your **WEBHOOK SECRET KEY**, you will need to parse and verify it before it can be used. This is performed in three steps:

* Split the signed request into two parts delineated by a '.' character \(eg. 238fsdfsd.oijdoifjsidf899\)
* Decode the first part - **the encoded signature** - from base64url
* Decode the second part - **the payload** - from base64url and then decode the resultant JSON object

These steps are possible in any modern programming language.

Examples :

{% tabs %}
{% tab title="PHP" %}
```php
<?php

function parse_signed_request($signed_request, $secret) {
  list($encoded_sig, $payload) = explode('.', $signed_request, 2); 

  // decode the data
  $sig = base64_url_decode($encoded_sig);
  $data = json_decode(base64_url_decode($payload), true);

  // confirm the signature
  $expected_sig = hash_hmac('sha256', $payload, $secret, $raw = true);
  if ($sig !== $expected_sig) {
    error_log('Bad Signed JSON signature!');
    return null;
  }

  return $data;
}

function base64_url_decode($input) {
  return base64_decode(strtr($input, '-_', '+/'));
}
```
{% endtab %}

{% tab title="Python" %}
```python
import hmac
import hashlib

def check_signature(request_signature, secret_key, request_body):

    hasher = hmac.new(secret_key, request_body, hashlib.sha256)
    dig = hasher.hexdigest()

    return hmac.compare_digest(dig, request_signature)

req_sig = '9d101d2bf630748679226b767d2031634c520390ff0e926afc09bc65a05bfdb2'
req_body = '4567'
secret_key = '1234'

print(check_signature(secret_key, req_sig, req_body))
```
{% endtab %}

{% tab title="Go" %}
```go
require 'openssl'

def check_signature(secret_key, request_signature, request_body)

  digest = OpenSSL::Digest.new('sha256')

  hmac = OpenSSL::HMAC.new(secret_key, digest)
  hmac.update(request_body)
  hmac.to_s == request_signature
end

# req_sig = request.headers['HTTP-RIMINDER-SIGNATURE']
# req_body = request.body.read
# secret_key = ENV['RIMINDER_WEBHOOK_KEY']

req_sig = '9d101d2bf630748679226b767d2031634c520390ff0e926afc09bc65a05bfdb2'
req_body = '4567'
secret_key = '1234'

puts check_signature(secret_key, req_sig, req_body)
```
{% endtab %}
{% endtabs %}

