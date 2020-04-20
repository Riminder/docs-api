# Profile

|  |  |
| :--- | :--- |
| Upload Profile | You can upload either json or binary \(file\) Profile |
| Upload by batch | Upload a folder |
| get Profile's attachment | Retrieve Profile's document |
| get Profile's tag | Retrieve Profile's tag |
| get Profile's metadata | Retrieve Profile's metadata |
| get Profile's parsing | Retrieve Profile's parsing |
| get Profile's revealing | Retrieve Profile's revealing |
| get Profile's embedding | Retrieve Profile's embedding |
| get Profile's searching | Profile search engine |
| get Profile's scoring | Retrieve Profile's scoring |
| get Profile's reasoning | Retrieve Profile's reasoning |

## Upload Profile:

#### Json :

This endpoint needs

* A **source id**: A source \(of profiles\) can be created or accessed at **https://`<your-sub domain/>`.hrflow.ai/sources**. It corresponds to a source of profiles.
* A python dictionary **profile\_json**: The profile to be added to the source. This input is shaped as a dictionary '{key:value}' pairs.
* \(Optional\) **profile\_tags**: A list of tags that needs to be associated to the profile
* \(Optional\) **profile\_reference**: A string reference that can be used to access your uploaded profile's features

Currently, **profile\_id** can only be retrieved through a webhook. The **item\_id** is only related to the upload and have no relationship with **profile\_id**.

Alternatively **profile\_reference** can be used instead of **profile\_id** to perform some tasks. However, only the creation of the **profile\_id guarantees the processing** of your profile \(parsing, revealing, embedding, etc\).

```php
$client->profile->add_json($source_id, $profile_data, $profile_reference, 
                           $timestamp_reception, $profile_labels, 
                           $profile_tags, $profile_metadatas);
```

#### File :

It takes two mandatory fields:

* **source id**: A source \(of profiles\) can be created or accessed at **https://`<your-sub domain/>`.hrflow.ai/sources**. It corresponds to a source of profiles.
* **profile\_file**: loaded binary file from disk using file object's read method
* \(optional\) **sync\_parsing**: either use fast parsing \(set value to 1\) or not \(set value to 0 or ignore it\). Default behavior uses asynchronous parsing.
* \(Optional\) **profile\_reference**: A string reference that can be used to access your uploaded profile's features

```php
$profile_file =fopen("path/to/file", "rb")
$client->profile->add_file($source_id, $profile_file, $profile_content_type, 
                           $profile_reference, $timestamp_reception, 
                           $profile_labels, $profile_tags, $profile_metadatas,
                           $sync_parsing);
```

{% hint style="info" %}
See [examples](https://developers.hrflow.ai/api-reference/profile-api/post-profile) 
{% endhint %}



The next 4 endpoints needs :

* **source id**: A source can be created or accessed at **https://`<your-sub domain/>`.hrflow.ai/sources**. It corresponds to a source of profiles.
* **profile\_id**: Retrievable through a webhook after an uploaded has been made. Alternatively, **profile\_reference** can be used if it has been set while uploading.

{% hint style="info" %}
You can use the ProfileID object
{% endhint %}

## Profile's Attachment Retrieval

Retrieve profile's documents associated with both profile id and source id

```php
client->profile->attachment->list($source_id, new ProfileID('profile_id'))
```

## Profile's Tag Retrieval

Retrieve profile's tag associated with both profile id and source id

```php
client->profile->tag->list($source_id, new ProfileID('profile_id'))
```

## Profile's Metadata Retrieval

Retrieve profile's metadata associated with both profile id and source id

```php
client->profile->metadata->list($source_id, new ProfileID('profile_id'))
```

##  Get Parsed Document

Retrieve profile's parsing associated with both profile id and source id

```php
client->profile->parsing->list($source_id, new ProfileID('profile_id'))
```

## Profile Search Engine

 This endpoint searches profiles from **source\_ids** \(a list of source\_id\) which follows a set of filtering fields \(stage: "yes", "no" or "new"; date\_start: timestamp as string; date\_end\)

```php
$client->profile->searching->get(array $source_ids, $name=null, $email=null, $location_geopoint=[], $location_distance=null, $summary_keywords=[], $text_keywords=[],
                    $experience_keywords=[], $experience_location_geopoint=[], $experience_location_distance=null, $experiences_duration_min=null, $experiences_duration_max=null,
                    $education_keywords=[], $education_location_geopoint=[], $education_location_distance=null, $educations_duration_min=null, $educations_duration_max=null,
                    $skills_dict=[], $languages_dict=[], $interests_dict=null, $labels_dict=null,
                    $date_start="1494539999", $date_end=null, $page=1, $limit=30, $sort_by='date_reception', $order_by='asc');
```

## Profile's Scoring

scores profiles from **source\_ids** \(a list of source\_id\) with regards to a **job\_id**. job\_id can retrieved using the **Job API** or by creating a new job at **https://`<your-sub domain/>`.hrflow.ai/marketplace/agents**. The underlying **scoring agent** \(classifier model\) is linked to the job\_id while creating the job

```php
$client->profile->scoring->get(array $source_ids, $job_id=null, $stage=null, $use_agent=null, $name=null, $email=null, $location_geopoint=[], $location_distance=null, $summary_keywords=[], $text_keywords=[],
                    $experience_keywords=[], $experience_location_geopoint=[], $experience_location_distance=null, $experiences_duration_min=null, $experiences_duration_max=null,
                    $education_keywords=[], $education_location_geopoint=[], $education_location_distance=null, $educations_duration_min=null, $educations_duration_max=null,
                    $skills_dict=[], $languages_dict=[], $interests_dict=null, $labels_dict=null,
                    $date_start="1494539999", $date_end=null, $page=1, $limit=30, $sort_by='date_reception', $order_by='asc');
```

## Embedding Retrieval

This endpoint returns embeddings for a given profile \(uniquely defined by the pair **source\_id** and **profile\_id**\). HRFlow provides multiple level of embedding **granularity**. You can either retrieve the overall profile embedding, the embedding associated to the n-th experiences or any other **fields**. The wanted embeddings for a profile needs to be specified through the 'fields' input variable.

This methods presently handles only profile per profile embeddings. A loop is required to get embeddings for more than one profile.

```php
$client->profile->embedding->get($source_id, new ProfileId("profile_id"), 
                                ['skills'=>1]);
```

