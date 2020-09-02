---
description: Welcome to tomorrow's HR automation platform
---

# Workflows

## Overview

The new HrFlow **Workflows** feature allows you to run your HR-related pipelines without ever worrying about servers. Whether you need to continuously run some routines or have a triggered execution both scenarios are possible with **Workflows**.   
  
Two main execution modes are available : _**Catch**_ and _**Pull**_. The _**Catch**_ mode is a _webhook-like_ setup that allows you to execute your code whenever a request is made to a precise endpoint. The **Pull** mode is similar to a _cron job_ which is executed at the rate of your choosing. In both modes, the code you submit **can leverage the `hrflow` sdk** to seamlessly create value with your HR data and HrFlow's **AI-Powered Job & Profile API**. 

## Workflow setup

**Workflows** is a _self-service_ that you can configure from the app by navigating to the dedicated section. If you click the top-right `Create Workflow`  a new window let's you choose the kind of _Webhook execution_ that you need.

Once created your workflow must be configured by clicking on it from the main **Workflows** section in the app.

{% hint style="info" %}
Content below is valid for **Python3.6** runtime. 
{% endhint %}

### Catch setup

The core of your **Catch** workflow is the `Function`  section. To execute your code you are exepected to write a function with this signature `def workflow(body: Dict, settings: Dict) -> None`

Two inputs are available to you code in this mode : 

* `body` is a dictionary containing the body of the request that triggered the workflow execution
* `settings` is a dictionary containing key/value pairs that you define in the **Environment Properties** 



