---
description: Hrflow SDK for Javascript
---

# Javascript

Our Javascript library is an open source, producrion-ready and a Javascript wrapper API. It is an easy way to access Hrflow API features from a node js server or from the browser.

This library is open-source, so you can [check it out on Github](https://github.com/Riminder/javascript-hrflow-api).

### Install

install hrflow client using [npm](https://www.npmjs.com/):

```text
npm install hrflow --save
```



### Initialize the client

To authenticate against the API, get your API SECRET KEY from your HrFlow dashboard!

To begin you adventure with HrFlow,  you will need to initialize the client. In order to do this you will need your **API SECRET KEY**. You can retrieve it from [HrFlow Dashboard](https://developers.hrflow.ai/getting-started/authentication)

```javascript
import Hrflow from 'hrflow'

const client = new Hrflow({API_Key: "your api key"});
```



## Methods

### Profile

| List of Methods |  |
| :--- | :--- |
| [Upload Profile](https://developers.hrflow.ai/api-reference/profile-api/post-profile) | You can upload either json or binary \(file\) Profile |
| [Get Profile's searching](https://developers.hrflow.ai/api-reference/profile-api/get-profiles-searching) | Profile search engine |
| [Get Profile's scoring](https://developers.hrflow.ai/api-reference/profile-api/get-profiles-scoring) | Retrieve Profile's scoring |
| [Get Profile's parsing](https://developers.hrflow.ai/api-reference/profile-api/get-profile-parsing) | Retrieve Profile's parsing |
| [Get Profile's embedding](https://developers.hrflow.ai/api-reference/profile-api/get-profile-embedding) | Retrieve Profile's embedding |
| [Get Profile's attachment](https://developers.hrflow.ai/api-reference/profile-api/get-profile-attachments) | Retrieve Profile's document |
| [Get Profile's tag](https://developers.hrflow.ai/api-reference/profile-api/get-profile-tags) | Retrieve Profile's tag |
| [Get Profile's metadata](https://developers.hrflow.ai/api-reference/profile-api/get-profile-metadatas) | Retrieve Profile's metadata |
| [Get Profile's revealing](https://developers.hrflow.ai/api-reference/profile-api/get-profile-revealing) | Retrieve Profile's revealing |
| [Get Profile's reasoning](https://developers.hrflow.ai/api-reference/profile-api/get-profile-reasoning) | Retrieve Profile's reasoning |

### Job

| List of methods |  |
| :--- | :--- |
| [Upload Job](https://developers.hrflow.ai/api-reference/job-api/post-job) | Uploading a job by specifying some information. |
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



