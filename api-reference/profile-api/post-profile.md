---
description: This endpoint allows you to add new profile to a given source.
---

# POST  /profile

{% hint style="info" %}
This endpoint requires at least source\_id
{% endhint %}

Please note that **complementary** information could be included :

* profile reference,
* profile's label \(.ie new, yes, later, no\) for given job and ratings,
* profile's tags,
* profile's metadata,
* reception date as timestamp.

This endpoint accepts both json and file profile's document. ****In order to identify whether you send a json or a file, there is a request parameter **profile\_type** that must be included in POST request.

#### 1\) Json profile :

Please find below an example of json profile that could be submitted.

```javascript
{
  "name": "Harry Potter",
  "email": "harry.potter@gmail.com",
  "address": "1 rue streeling",
  "info" : {
      "name":"Harry Potter",
      "email":"harry.potter@gmail.com",
      "phone":"0202",
      "location":"somewhere",
      "urls": {
          "from_resume": [],
          "linkedin":"",
          "twitter":"",
          "facebook":"",
          "github":"",
          "picture":""},
      "location":{"text":""}},
  "summary": "test summary",
  "experiences": [{
      "start": "15/02/1900",
      "end": "",
      "title": "Lead",
      "company": "Mathematic Departement",
      "location": {"text":"Paris"},
      "description": "Developping."
      }],
  "educations": [{
      "start": "12540",
      "end": "12550",
      "title": "Mathematicien",
      "school": "University",
      "description": "Description",
      "location": {"text":"Scotland"}
  }],
  "skills": ["manual skill", "Creative spirit", "Writing skills", "Communication"],
  "languages" : ["english"],
  "interests": ["football"],
  "tags":[],
  "metadatas":[],
  "labels":["stage":"yes","job_id":"job_id"]
}
```

{% api-method method="post" host="https://api.hrflow.ai/v1" path="/profile" %}
{% api-method-summary %}
/profile \(Json\)
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

{% api-method-form-data-parameters %}
{% api-method-parameter name="source\_id" type="string" required=true %}
Source id
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_json" type="object" required=true %}
Profile's json
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_type" type="string" required=true %}
json
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_reference" type="string" required=false %}
Profile's reference
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_labels" type="array" required=false %}
Profile's labels  
\(ie \[{"job\_id": "job\_id", "job\_reference": "test", "stage": "yes", "stage\_timestamp":1585662186, "rating":0.5, "stage\_timestamp":1585662286}\]
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_tags" type="array" required=false %}
Profile's tags  
\(ie \[{"name":"blacklist", "value":True}, ...\]
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_metadatas" type="array" required=false %}
Profile's metadata  
\(ie \[{"name":"email", "value":"test@test.com"}, ...} 
{% endapi-method-parameter %}

{% api-method-parameter name="timestamp\_reception" type="string" required=false %}
Reception date as timestamp
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Profile successfully created using async parsing.
{% endapi-method-response-example-description %}

```javascript
{
    "code": 201,
    "message": "Profile file added",
    "data": {
        "item_id': "item_id",
        "item_type": "json"
     }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=202 %}
{% api-method-response-example-description %}
Profile successfully created using sync parsing.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 202,
    "message": "Profile file added",
    "data": {
        "item_id": "item_id",
        "item_type": "json"
     }
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
    "message": "Bad Request. Invalid source_id:xxxx"
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
    "message": "Unauthorized. Invalid secret key: xxxxx "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Example

{% tabs %}
{% tab title="PHP" %}
```php
$client->profile->add_json($source_id, $profile_d, $profile_reference, 
                           $timestamp_reception, $profile_labels, 
                           $profile_tags, $profile_metadatas);
```
{% endtab %}

{% tab title="Python" %}
```python
client.profile.add_json(source_id="source_id", 
                        profile_json=profile_json,
                        profile_tags =[{"name": "email", "value":"test@test.com"}])
```
{% endtab %}
{% endtabs %}

#### 2\) File profile :

All possible extensions of a valid profile's resume are accepted \(.ie pdf, png, jpeg, docx, ppt, rtbf, html ...\)

{% hint style="info" %}
Only files could use synchronized parsing.
{% endhint %}

{% api-method method="post" host="https://api.hrflow.ai/v1" path="/profile" %}
{% api-method-summary %}
Post /profile \(File\)
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

{% api-method-form-data-parameters %}
{% api-method-parameter name="source\_id" type="string" required=true %}
Source id
{% endapi-method-parameter %}

{% api-method-parameter name="file" type="object" required=true %}
Profile's document
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_type" type="string" required=true %}
file
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_content\_type" type="string" required=false %}
Document content type \(ie application/pdf\)
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_reference" type="string" required=false %}
Profile's reference
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_labels" type="array" required=false %}
Profile's label  
\(ie \[{"job\_id": "job\_id", "job\_reference": "test", "stage": "yes", "stage\_timestamp":1585662186, "rating":0.5, "stage\_timestamp":1585662186}, ...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_tags" type="array" required=false %}
Profile's tags  
\(ie \[{"name":"blacklist","value":True}, ...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_metadatas" type="array" required=false %}
Profile's metadata         
\(ie \[{"name":"mail","value":"test@test.com"}, ...\]\)
{% endapi-method-parameter %}

{% api-method-parameter name="timestamp\_reception" type="integer" required=false %}
Reception date as timestamp
{% endapi-method-parameter %}

{% api-method-parameter name="sync\_parsing" type="boolean" required=false %}
Using synchronize parsing
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Profile successfully Created using async parsing.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 201,
    "message": "Profile file added",
    "data": {
        "item_id": "item_id",
        "item_type": "file"
     }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=202 %}
{% api-method-response-example-description %}
Profile successfully Created using sync parsing.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 202,
    "message": "Profile file added",
    "data": {
        "profile": {...}
     }
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
    "message": "Bad Request. Invalid source_id:xxxx"
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
    "message": "Unauthorized. Invalid secret key: xxxxx "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



While uploading a profile file you can use either **synchronous** or **asynchronous** parsing:

**Asynchronous parsing:**

As explained in this diagram, parsing **** will be done **asynchronously** as soon as it is available. Then you will receive a webhook notification for success or failure of profile parsing.

![](../../.gitbook/assets/asyncparsing-diagram.png)

**Synchronous parsing:**

For synchronous parsing , you will receive profile parsing in the response body.

![](../../.gitbook/assets/syncparsing-diagram.png)

**sync\_parsing** is an optional request parameter , you can set its value to 1 to use sync parsing or set its value to 0 to use async parsing.  
 The default behavior uses asynchronous parsing.  
  
So as to Use Sync Parsing, you need to:

* Create an API source \(HTTP / Python / PHP ...\),
* Enable SyncParsing for a given Source :
  * Your admin must activate SyncParsing  in source's configuration,
  * Send a request to HrFlow support team in order to enable this feature for you.
* Set sync\_parsing to 1 in your request

### Example

{% tabs %}
{% tab title="PHP" %}
```php
$profile_file = fopen('/path/to/file.pdf','rb');

$client->profile->add_file($source_id, $profile_file, $profile_content_type, 
                           $profile_reference, $timestamp_reception, 
                           $profile_labels, $profile_tags, $profile_metadatas,
                           $sync_parsing);
```
{% endtab %}

{% tab title="Python" %}
```python
with open('/path/to/file.pdf','rb') as file:
    profile_file = file.read()
    
client.profile.add_file(source_id="source_id",
                        profile_file=profile_binary,
                        profile_content_type='application/pdf',
                        profile_labels=[]
                        profile_tags=[{"name" : "email", "value": "test@hrflow.ai"},
                                      {"name" : "blacklist", "value": True}],
                        profile_metadata=[],
                        timestamp_reception=1587398379
                        sync_parsing=0)
```
{% endtab %}
{% endtabs %}





