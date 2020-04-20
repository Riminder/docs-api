---
description: HrFlow SDK for PHP
---

# PHP

Our PHP library is an open source,  production-ready and a PHP Wrapper API. It is an easy way to access HrFlow API features  .

This library is open-source, so you can [check it out on GitHub](https://github.com/Riminder/php-hrflow-api).

## Install

#### With Composer \(recommended\)

Install the package via [Composer](https://packagist.org/packages/hrflow/hrflow-php-api):

```bash
composer require hrflow/hrflow-php-api
```

#### Without Composer

1\) Clone the repository from [GitHub](https://github.com/Riminder/php-hrflow-api).

```bash
git clone https://github.com/Riminder/php-hrflow-api.git /folder/path
```

2\) Then you must add the following code to your PHP script to actually load the HrFlow:

```text
require_once("/path/to/php-hrflow-api/ressources/Client.php");
```

{% hint style="info" %}
You can keep the API client up to date by checking [GitHub release page](https://github.com/Riminder/php-hrflow-api/releases).
{% endhint %}

## Initialize the client

To authenticate against the API, get your API SECRET KEY from your HrFlow dashboard!

To begin you adventure with HrFlow,  you will need to initialize the client. In order to do this you will need your **API SECRET KEY**. You can retrieve it from [HrFlow Dashboard](https://developers.hrflow.ai/getting-started/authentication)

```php
require __DIR__ . '/vendor/autoload.php';

// Authentication to api
$client = new Client('yourShinyKey');
```





