---
description: This endpoint allows you to add new profile using resume to a given source.
---

# \[POST\]  /profile/parsing/file

Supported extensions for the parsing API are .pdf, .png, .jpg, .jpeg, .bmp, .doc, .docx, .odt, .rtf, .odp, ppt, and .pptx .

{% api-method method="post" host="https://api.hrflow.ai" path="/v1/profile/parsing/file" %}
{% api-method-summary %}
Post /profile/parsing/file
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token
{% endapi-method-parameter %}

{% api-method-parameter name="X-USER-EMAIL" type="string" required=true %}
User's email
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="source\_key" type="string" required=true %}
Source key
{% endapi-method-parameter %}

{% api-method-parameter name="file" type="object" required=true %}
Profile's file resume
{% endapi-method-parameter %}

{% api-method-parameter name="sync\_parsing" type="integer" required=false %}
Use sync parsing \(ie. 0 or 1\)  
Default is 0
{% endapi-method-parameter %}

{% api-method-parameter name="sync\_parsing\_indexing" type="integer" required=false %}
Index sync parsing results \(ie. 0 or 1\)  
Default is 0
{% endapi-method-parameter %}

{% api-method-parameter name="webhook\_parsing\_sending" type="integer" required=false %}
Receive webhook parsing success notification  
\(ie. 0 or 1\)  
Default is 0
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_content\_type" type="string" required=false %}
Document content type \(ie application/pdf\)
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=false %}
Profile's reference
{% endapi-method-parameter %}

{% api-method-parameter name="labels" type="array" required=false %}
Profile's labels  
\(ie \[{"job\_key": "job\_key", "job\_reference": "test", "stage": "yes", "stage\_timestamp":1585662186, "rating":0.5, "stage\_timestamp":1585662186}, ...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="tags" type="array" required=false %}
Profile's tags  
\(ie \[{"name":"blacklist","value":true}, ...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="metadatas" type="array" required=false %}
Profile's metadata         
\(ie \[{"name":"mail","value":"test@test.com"}, ...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="created\_at" type="string" required=false %}
Reception date as iso format
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Profile successfully Created using sync parsing.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 201,
    "message": "Profile parsed successfully. Profile extraction finished : 7.279723644256592 seconds.",
    "data": {
        "parsing": {...},
        "profile": {...}
     }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=202 %}
{% api-method-response-example-description %}
Profile successfully Created using async parsing.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 202,
    "message": "Your profile as been sent successfully to the Parsing Queue.",
    "data": []
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a source matching this query.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 400,
    "message": "Invalid source fields"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Invalid secret key.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 401,
    "message": "Unauthorized. Invalid secret key: xxxx for permission: write"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



While uploading a profile file you can use either **synchronous** or **asynchronous** parsing:

### **Asynchronous parsing:**

As explained in this diagram, parsing **** will be done **asynchronously** as soon as it is available. Then you will receive a webhook notification for success or failure of profile parsing.

![](../../.gitbook/assets/asyncparsing-diagram.png)

**Synchronous parsing:**

For synchronous parsing , you will receive profile parsing in the response body.

![](../../.gitbook/assets/syncparsing-diagram.png)

**sync\_parsing** is an optional request parameter , you can set its value to 1 to use sync parsing or set its value to 0 to use async parsing.

The default behavior uses asynchronous parsing.  
  
So as to Use Sync Parsing, you need to:

* Create an API source \(HTTP / Python / PHP ...\),
* Enable `sync_parsing` for a given Source :
  * Your admin must activate `sync_parsing`  in source's configuration,
  * Send a request to HrFlow support team in order to enable this feature for you.
* Set `sync_parsing` to 1 in your request

### What's a **profile\_key and how to retrieve it ?**

A profile ID is a unique identifier for a **HrFlow Profile**. This information is mandatory, **`profile_key` guarantees the processing** of your profile \(parsing, revealing, embedding, etc\).

**How to get a profile\_key**

If you are using SyncParsing you will receive profile\_key in the response's body  and if you are using the AsyncParsing you have 3 possible ways that help you retrieve this information.

* Upload your document with a `reference`, thus you can get profile's parsing from [this endpoint](https://developers.hrflow.ai/api-reference/profile-api/get-profile-parsing) using `source_key` and `reference`,
* Set up a webhook that listens to all incoming notifications from HrFlow. As soon as your document is well parsed you will receive a success event including  the profile id,
* Use HrFlow's Profile Search Engine, in order to find profile's details, then you can fetch for profile\_key.

### Example

{% tabs %}
{% tab title="PHP" %}
```php
$client = new Hrflow\Client('your api key');

$data = [
  'timestamp_reception'   => 1569320033,  
  'profile_content_type'  => 'application/pdf', 
  'profile_reference'     => 'profile_reference', 
  'profile_labels'        =>  [
    [
      'job_id'           => 'job_id',
      'stage'            => 'yes',
      'stage_timestamp'  => 1585662186,
      'rating'           => 0.5,
      'stage_timestamp'  => 1585662186
    ], 
    ...
  ],
  'profile_metadatas' => [["name" => "mail", "value" => "test@test.com"], ...],
]
$profile_file = fopen('/path/to/file.pdf','rb');

$client->profile::addFile($source_id, $profile_file, $data);
```
{% endtab %}

{% tab title="Python" %}
```python
import hrflow as hf

client = hf.client(api_secret="Your API Key", api_user="Your API user email",=)

with open('/path/to/file.pdf','rb') as file:
    profile_file = file.read()
    
client.profile.parsing.add_file(source_key="source_key",
                        profile_file=profile_file,
                        profile_content_type='application/pdf',
                        reference='profile_reference',
                        labels=[
                          {
                            "job_key": "job_key",
                            "job_reference": "test",
                            "stage": "yes",
                            "stage_timestamp":1585662186,
                            "rating":0.5,
                            "stage_timestamp":1585662186
                          }, 
                        ],
                        tags=[{"name":"blacklist","value":true}],
                        metadatas=[{"name":"mail","value":"test@test.com"}, ...],
                        created_at: "2016-01-01T00:00:00",
                        sync_parsing=0,
                        sync_parsing_indexing=1,
                        webhook_parsing_sending=0)
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
import * as fs from 'fs';
import Hrflow from 'hrflow';
const client = new Hrflow({
    api_secret: 'Your API Key',
    api_user: 'Your API user email',
});

client.profile.parsing.addFile('source_key',
  fs.createReadStream('path to your file'), {
    sync_parsing: 1,
    created_at: '2016-01-01T00:00:00',
    metadatas: [{'name':'mail','value':'test@test.com'}],
    profile_content_type: 'application/pdf', 
    profile_reference: 'profile_reference',
    labels:  [
      {
        'job_key': 'job_key',
        'job_reference': 'test',
        'stage': 'yes',
        'stage_timestamp':1585662186,
        'rating':0.5,
        'stage_timestamp':1585662186
      }, 
    ],
    tags:  [{ name: 'blacklist', value: true}],
}).then(response => {
    console.log(response);
});
```
{% endtab %}
{% endtabs %}





