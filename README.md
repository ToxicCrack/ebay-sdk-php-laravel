# eBay SDK for PHP

This is a fork of [BenMorel/ebay-sdk-php](https://github.com/BenMorel/ebay-sdk-php) by [@benmorel](https://github.com/BenMorel) which is a fork of the original [dts/ebay-sdk-php](https://github.com/davidtsadler/ebay-sdk-php) by [@davidtsadler](https://github.com/davidtsadler), with support for PHP 7.3, PHP 7.4 and PHP 8, and compatibility with Laravel 10.

The original project has been officially abandoned in February 2020.


[![Build Status](https://github.com/benmorel/ebay-sdk-php/workflows/CI/badge.svg)](https://github.com/benmorel/ebay-sdk-php/actions)
[![Latest Stable Version](https://poser.pugx.org/benmorel/ebay-sdk-php/v/stable)](https://packagist.org/packages/benmorel/ebay-sdk-php)
[![Total Downloads](https://poser.pugx.org/benmorel/ebay-sdk-php/downloads)](https://packagist.org/packages/benmorel/ebay-sdk-php)
[![License](https://img.shields.io/github/license/benmorel/ebay-sdk-php)](https://opensource.org/license/apache-2-0/)
---

This project enables PHP developers to use the eBay API in their PHP code, and build software using services such as Finding, Trading, Shopping, etc.

This is a personal project that was originally developed by David T. Sadler, who decided to create this project to make up for the lack of an official SDK for PHP. It is in no way endorsed, sponsored or maintained by eBay.

## Features

  - Compatible with PHP 7.2+ or PHP 8.0+.
  - Easy to install with [Composer](http://getcomposer.org/).
  - Compliant with [PSR-1](http://www.php-fig.org/psr/psr-1/), [PSR-2](http://www.php-fig.org/psr/psr-2/) and [PSR-4](http://www.php-fig.org/psr/psr-4/).

## Requirements

  - PHP 7.2+ or PHP 8.0+ with the following extensions:
      - curl
      - libxml
  - 64 bit version
  - SSL enabled on the cURL extension so that https requests can be made.

## Installation

The SDK can be installed with [Composer](http://getcomposer.org/):

```
composer require toxiccrack/ebay-sdk-php-laravel
```

## Example

### Get the official eBay time

```php
<?php

require 'vendor/autoload.php';

use DTS\eBaySDK\Shopping\Services;
use DTS\eBaySDK\Shopping\Types;

// Create the service object.
$service = new Services\ShoppingService();

// Create the request object.
$request = new Types\GeteBayTimeRequestType();

// Send the request to the service operation.
$response = $service->geteBayTime($request);

// Output the result of calling the service operation.
printf(
    "The official eBay time is: %s\n",
    $response->Timestamp->format('H:i (\G\M\T) \o\n l jS Y')
);
```

More examples can be found in the [ebay-sdk-examples](https://github.com/davidtsadler/ebay-sdk-examples) repository.

## License

Licensed under the [Apache Public License 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).

Copyright 2016 David T. Sadler.
