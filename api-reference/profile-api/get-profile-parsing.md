---
description: Retrieve profile's parsing given profile id and source_id.
---

# \[GET\] /profile/parsing

{% hint style="info" %}
This endpoint requires either profile\_id or profile\_reference or profile\_email.
{% endhint %}

{% api-method method="get" host="https://api.hrflow.ai/v1" path="/profile/parsing" %}
{% api-method-summary %}
Get /profile/parsing
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get parsing's result of a given profile.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-API-KEY" type="string" required=true %}
Authentication token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="source\_id" type="string" required=true %}
source id.
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_id" type="string" required=true %}
profile id.
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_reference" type="string" required=false %}
profile reference.
{% endapi-method-parameter %}

{% api-method-parameter name="profile\_email" type="string" required=false %}
profile email.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Parsing successfully retrieved.
{% endapi-method-response-example-description %}

```scheme
{
    "code": 200,
    "message": "Profile parsing",
    "data":{
                "date_creation": "2019-01-15T12:09:58",
                "date_reception": "2019-01-15T12:09:42",
                "educations": [
                    {
                        "description": "Hogwarts School of Witchcraft and Wizardry",
                        "end_date": {
                            "date": null,
                            "text": null
                        },
                        "id": "education_id",
                        "location": {
                            "geocoder": {
                                "fields": {
                                    "category": null,
                                    "city": null,
                                    "city_district": null,
                                    "country": Scotland,
                                    "country_region": null,
                                    "entrance": null,
                                    "house": null,
                                    "house_number": null,
                                    "island": null,
                                    "level": null,
                                    "near": null,
                                    "po_box": null,
                                    "postcode": null,
                                    "road": null,
                                    "staircase": null,
                                    "state": null,
                                    "state_district": null,
                                    "suburb": null,
                                    "unit": null,
                                    "world_region": null
                                },
                                "gmaps": null,
                                "is_correct": null,
                                "lat": null,
                                "lng": null,
                                "text": null
                            },
                            "geopoint": {
                                "lat": null,
                                "lon": null
                            },
                            "text": null
                        },
                        "school": "Hogwarts",
                        "start_date": {
                            "date": "2013-01-01T01:00:00",
                            "text": "2013-2017"
                        },
                        "title": "MASTER IN APPLIED MATHEMATICS AND SIGNAL PROCESSING"
                    },
                    .
                    .
                    .
                    ],
                "educations_duration": n,
                "email": {
                    "text": "harry.potter@gmail.com"
                },
                "experiences": [
                    {
                        "company": "Gryffindor",
                        "description": "Chemistry – Potioneer.",
                        "end_date": {
                            "date": null,
                            "text": null
                        },
                        "id": "experience_id",
                        "location": {
                            "geocoder": {
                                "fields": {
                                    "category": null,
                                    "city": null,
                                    "city_district": null,
                                    "country": null,
                                    "country_region": null,
                                    "entrance": null,
                                    "house": null,
                                    "house_number": null,
                                    "island": null,
                                    "level": null,
                                    "near": null,
                                    "po_box": null,
                                    "postcode": null,
                                    "road": null,
                                    "staircase": null,
                                    "state": null,
                                    "state_district": null,
                                    "suburb": null,
                                    "unit": null,
                                    "world_region": null
                                },
                                "gmaps": "https://www.google.com/maps/place/1.29019,103.85199",
                                "is_correct": true,
                                "lat": 1.2901899814605713,
                                "lng": 103.85198974609375,
                                "text": "Singapore"
                            },
                            "geopoint": {
                                "lat": 1.2901899814605713,
                                "lon": 103.85198974609375
                            },
                            "text": "Singapore"
                        },
                        "start_date": {
                            "date": "2017-03-01T01:00:00",
                            "text": "March 2017-September 2017"
                        },
                        "title": "Machine Learning Engineer"
                    },
                    .
                    .
                    .
            
                ],
                "experiences_duration": 1.2547945205479452,
                "interests": [
                    {
                        "name": "Psychology",
                        "value": null
                    }
                ],
                "labels": [
                    {
                        "date_rating": "2019-07-15T14:51:07",
                        "date_stage": "2019-07-15T14:51:07",
                        "job_id": "job_id",
                        "job_reference": "19051996",
                        "rating": null,
                        "stage": "yes"
                    }
                ],
                "languages": [
                    {
                        "name": "english",
                        "value": null
                    },
                    {
                        "name": "french",
                        "value": null
                    }
                ],
                "location": {
                    "geocoder": {
                        "fields": {
                            "category": null,
                            "city": null,
                            "city_district": null,
                            "country": null,
                            "country_region": null,
                            "entrance": null,
                            "house": null,
                            "house_number": null,
                            "island": null,
                            "level": null,
                            "near": null,
                            "po_box": null,
                            "postcode": null,
                            "road": null,
                            "staircase": null,
                            "state": null,
                            "state_district": null,
                            "suburb": null,
                            "unit": null,
                            "world_region": null
                        },
                        "gmaps": null,
                        "is_correct": null,
                        "lat": null,
                        "lng": null,
                        "text": null
                    },
                    "geopoint": {
                        "lat": null,
                        "lon": null
                    },
                    "text": null
                },
                "name": {
                    "first_name": "Harry",
                    "last_name": "Potter",
                    "text": "Harry Potter"
                },
                "profile_id": "profile_id",
                "skills": [
                    {
                        "is_predicted": false,
                        "name": "Chemistry",
                        "type": "hard_skill",
                        "value": null
                    },
                    {
                        "is_predicted": false,
                        "name": "Mathematics",
                        "type": "hard_skill",
                        "value": null
                    },
                    {
                        "is_predicted": false,
                        "name": "algorithms",
                        "type": "hard_skill",
                        "value": null
                    },
                    {
                        "is_predicted": false,
                        "name": "Psychology",
                        "type": "soft_skill",
                        "value": null
                    },
                    
                ],
                "source_id": "source_id",
                "summary": "Bayesian Optimization",
                "team_id": "team_id",
                "text": {
                    "ar": "",
                    "bg": "",
                    "bn": "",
                    "ca": "",
                    "cjk": "",
                    "cs": "",
                    "da": "",
                    "de": "",
                    "el": "",
                    "en": "Description",
                    "es": "",
                    "eu": "",
                    "fa": "",
                    "fi": "",
                    "fr": "",
                    "ga": "",
                    "gl": "",
                    "hi": "",
                    "hu": "",
                    "hy": "",
                    "id": "",
                    "it": "",
                    "ku": "",
                    "lt": "",
                    "lv": "",
                    "nl": "",
                    "no": "",
                    "pt": "",
                    "pt-BR": "",
                    "ro": "",
                    "ru": "",
                    "sv": "",
                    "th": "",
                    "tr": ""
                },
                "urls": {
                    "facebook": null,
                    "from_resume": [],
                    "github": null,
                    "linkedin": null,
                    "picture": null,
                    "twitter": null
                },
                "uuid": "H60lHC-0EemVogJCrBEAAw"
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
    "message": "Invalid source array"
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
client->profile->parsing->list($source_id, new ProfileID('profile_id'))
```
{% endtab %}

{% tab title="Python" %}
```python
client.profile.parsing.get(source_id="source_id",
                           profile_id="profile_id")
```
{% endtab %}
{% endtabs %}

