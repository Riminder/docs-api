# Job

| List of methods |  |
| :--- | :--- |
| add Job as json file | Uploading a job by specifying some information. |
| get job's parsing | Retrieve Job's parsing |
| get job's embedding | Retrieve Job's embedding for advanced anlaysis |
| Job searching | Job search engine |
| Job Scoring | Planned for future release  |
| Job Reasoning | Planned for future release  |

## Upload Json

```php
$job_json = [
     "title"       => "Data engineer",
     "description" => "This job is made for you"
] ;
$client->job->add_json("name", "agen_id", "job_reference", "job_tags", 
                         "job_metadatas", "timestamp_reception", $job_json);
```

### Get Parsed Document

 retrieves the information of a given job. It uses one mandatory field: **job\_id**. The job\_id is returned as part of a response's upload.

{% hint style="info" %}
You can use the JobID object
{% endhint %}

```php
$client->job->parsing->get(new JobID("job_id"));
```

### Embedding Retrieval

This endpoint returns embedding for a given job \(uniquely defined by the pair **source\_id** and **job\_id**\).

This methods presently handles only job per job embedding. A loop is required to get embedding for more than one job.

{% hint style="info" %}
You can use the JobID object
{% endhint %}

```php
$client->job->parsing->get(new JobID("job_id"));
```

## Job Search Engine

searches jobs based on their **name**

```php
$client->job->searching->get('name');
```

