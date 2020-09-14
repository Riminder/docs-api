---
description: Welcome to tomorrow's HR automation platform
---

# Workflows

## Overview

The new HrFlow **Workflows** feature allows you to run your HR-related pipelines without ever worrying about servers. Whether you need to continuously run some routines or have a triggered execution both scenarios are possible with **Workflows**.   
  
Two main execution modes are available: _**Catch**_ and _**Pull**_. The _**Catch**_ mode is a _webhook-like_ setup that allows you to execute your code whenever a request is made to a precise endpoint. The **Pull** mode is similar to a _cron job_ which is executed at the rate of your choosing. In both modes, the code you submit **can leverage the `hrflow` sdk** to seamlessly create value with your HR data and HrFlow's **AI-Powered Job & Profile API**. 

## Workflow setup

**Workflows** is a _self-service_ that you can configure from the app by navigating to the dedicated section. If you click the top-right `Create Workflow`  button a new window lets you choose the kind of _workflow execution_ that you need.

Once created your workflow must be configured by clicking on it from the main **Workflows** section in the app.

{% hint style="info" %}
Content below is valid for **Python3.6** runtime. 
{% endhint %}

### Catch setup

The core of your **Catch** workflow is the `Function`  section. To execute your code you are expected to write a function with this signature `def workflow(body: Dict, settings: Dict) -> None`

Two arguments are available to your code in this mode : 

* `body` is a dictionary containing the body of the request that triggered the workflow execution
* `settings` is a dictionary containing data that you defined in the **Environment Properties** section. It can also be used a way to store data that get persisted from one execution to another. Mind that both the key and value should **be natively JSON serializable**. For example, it won't work with `Python` `datetime.datetime.now()`

To illustrate let's consider this example where you process the event sent by some third-party service to add a new file to your HrFlow profile database.  

The main steps are :

* Setting up the `Hrflow` client with credentials stored in `settings`
* Parse the request `body` to retrieve relevant data
* Notify some other internal service that a new profile was added to HrFlow

```python
import requests

from hrflow import Hrflow

def workflow(body, settings):
    client = Hrflow(api_secret=settings["API_KEY"], api_user=settings["USER_EMAIL"])
    
    file_url = body["file_url"]
    file_content = requests.get(file_url, allow_redirects=True).content
    
    client.profile.parsing.add_file(
        source_key=settings["SOURCE_KEY"]),
        profile_file=file_content,
        profile_content_type="application/pdf",
        reference="profile_reference"
    )
    
    requests.post(settings["OTHER_SERVICE_URL"], data={"key": "value"})
```

![](../.gitbook/assets/screen-shot-2020-09-09-at-18.10.29.png)

For that code to execute correctly you must fill in the appropriate **environment properties** in the `Function` section of that particular **Catch** workflow. 

Once this is done you are all set! The **Catch** hook Url is ready to be used.

![](../.gitbook/assets/screen-shot-2020-09-04-at-09.26.38.png)

```bash
curl -X POST https://api-workflows.hrflow.ai/teams/XXX/YYY/python3.6/ZZZ \
    -H Content-Type:application/json \
    -d '{"file_url": "https://company.storage.fr/file/profile_1.doc"}'
```

{% hint style="danger" %}
**Important**: The endpoint provided expects to receive a **POST** request with a **valid JSON payload**. Using other HTTP methods or sending **multipart/form-data** won't work.
{% endhint %}

### Pull setup

The **Pull** setup is almost identical to the **Catch** one except for these two differences:

* The execution is not triggered by a request to some endpoint. The code is run continuously at the rate of your choosing
* Your function doesn't have access to a `body` argument. The expected signature is shorter `def workflow(settings: Dict) -> None:`

Here is a workflow that uses a static endpoint to perform periodic fetching and storing of data in HrFlow. This example illustrates the storage capabilities of `settings`. 

```python
from hrflow import Hrflow

INTERNAL_ENDPOINT = "https://storage.company.com/records"

def workflow(settings):
    client = Hrflow(api_secret=settings["API_KEY"], api_user=settings["USER_EMAIL"])
    
    last_uid = settings["LAST_UID"]
    data = request.get("{}?last_uid={}".format(INTERNAL_ENDPOINT, last_uid)).json()
    for file_url in data["files"]:
        file_content = requests.get(file_url, allow_redirects=True).content
        
        client.profile.parsing.add_file(
            source_key=settings["SOURCE_KEY"]),
            profile_file=file_content,
            profile_content_type="application/pdf",
            reference="profile_reference"
        )
    
    # Update LAST_UID
    settings["LAST_UID"] = data["last_uid"]
```

