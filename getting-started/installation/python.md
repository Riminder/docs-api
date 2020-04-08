---
description: HrFlow SDK for Python
---

# Python

## Introduction

3 packages have been developed to help using our Riminder API with the Python language:

* [python-hrflow-api](https://github.com/Riminder/python-hrflow-api): our main python wrapper to access our API features

## Installation

To use the API, you need Python 3 \(version **&gt;= 3.5**\) and **pip** which is a dependency manager.  
Installing the HrFlow package is as simple as writing this in the terminal :

```bash
pip3 install hrflow
```

You can now start to use the API.

## Usage

### Authentification

To authenticate against the api, get your API SECRET KEY from your HrFlow dashboard!

Then create a new Client`Hrflow` object with this key:

```python
import hrflow as hf
client = hf.Client(api_secret="YOUR_API_KEY")
```

### Overview

```python
import hrflow as hf
client = hf.Client(api_secret="YOUR_API_KEY")
result = client.source.search()
print(result)
```



