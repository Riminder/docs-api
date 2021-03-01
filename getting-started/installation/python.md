---
description: HrFlow.ai Python installation guide.
---

# Python SDK

Our Python library is an open source, production-ready and a Python Wrapper API. It is an easy way to access HrFlow API features .

This library is open-source, so you can [check it out on GitHub](https://github.com/Riminder/python-hrflow-api).

## Install

Install`hrflow`client using [pip](https://pypi.org/project/pip/):

```text
pip3 install hrflow
```

{% hint style="info" %}
You can keep the API client up to date by checking [GitHub release page](https://github.com/Riminder/python-hrflow-api/releases).
{% endhint %}

## Initialize the client

To authenticate against the API, get your API SECRET KEY from your HrFlow dashboard!

To begin you adventure with HrFlow, you will need to initialize the client. In order to do this you will need your **API SECRET KEY**. You can retrieve it from [HrFlow Dashboard](https://developers.hrflow.ai/getting-started/authentication)

```python
from hrflow import Hrflow

client = Hrflow(api_secret="your api key")
```

## Methods

### Profile

| List of Methods |  |
| :--- | :--- |
| [Upload Profile](https://developers.hrflow.ai/api-reference/profile-api/post-profile) | You can upload either json or binary \(file\) Profile |
| [Get Profile's searching](https://developers.hrflow.ai/api-reference/profile-api/get-profiles-searching) | Profile search engine |
| [Get Profile's scoring](https://developers.hrflow.ai/api-reference/profile-api/get-profiles-scoring) | Retrieve Profile's scoring |
| [Get Profile's indexing](../../api-reference/profile-api/get-profile-indexing.md) | Retrieve Profile's indexing JSON |
| [Get Profile's parsing](https://developers.hrflow.ai/api-reference/profile-api/get-profile-parsing) | Retrieve Profile's parsing |
| [Get Profile's embedding](https://developers.hrflow.ai/api-reference/profile-api/get-profile-embedding) | Retrieve Profile's embedding |
| [Get Profile's revealing](https://developers.hrflow.ai/api-reference/profile-api/get-profile-revealing) | Retrieve Profile's revealing |
| [Get Profile's reasoning](https://developers.hrflow.ai/api-reference/profile-api/get-profile-reasoning) | Retrieve Profile's reasoning |

### Job

| List of methods |  |
| :--- | :--- |
| [Upload Job](https://developers.hrflow.ai/api-reference/job-api/post-job) | Uploading a job by specifying some information. |
| [Get Job's indexing](../../api-reference/job-api/get-job.md) | Retrieve Job's indexing JSON |
| [Get job's parsing](https://developers.hrflow.ai/api-reference/job-api/get-job-parsing) | Retrieve Job's parsing |
| [Get job's embedding](https://developers.hrflow.ai/api-reference/job-api/get-job-embedding) | Retrieve Job's embedding for advanced analysis |
| [Job searching](https://developers.hrflow.ai/api-reference/job-api/get-job-searching) | Job search engine |
| [Job Scoring](https://developers.hrflow.ai/api-reference/job-api/get-jobs-scoring) | Retrieve scoring for list of jobs |
| [Job Reasoning](https://developers.hrflow.ai/api-reference/job-api/get-jobs-reasoning) | Retrieve Job's reasoning |

### Source

| List of methods |  |
| :--- | :--- |
| [List all sources](https://developers.hrflow.ai/api-reference/source-api/get-sources) | Method used for finding list of sources by the given condition |
| [Get a source](https://developers.hrflow.ai/api-reference/source-api/get-source) | Retrieve source's information for a given source\_id |

### Webhook

| List of methods |  |
| :--- | :--- |
| [Check webhook](https://developers.hrflow.ai/api-reference/events/authentification) | Send a webhook notification test |

