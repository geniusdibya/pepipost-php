![pepipostlogo](https://pepipost.com/assets/img/pepipost-footLogo.png)

[![Packagist](https://img.shields.io/packagist/php-v/pepipost/pepipost-sdk-php.svg?style=flat-square)](https://packagist.org/packages/pepipost/pepipost-sdk-php)
[![Packagist](https://img.shields.io/packagist/dt/pepipost/pepipost-sdk-php.svg?style=flat-square)](https://packagist.org/packages/pepipost/pepipost-sdk-php)
[![Packagist](https://img.shields.io/github/contributors/pepipost/pepipost-sdk-php.svg)](https://github.com/pepipost)
[![Packagist](https://img.shields.io/packagist/l/pepipost/pepipost-sdk-php.svg)](https://packagist.org/packages/pepipost/pepipost-sdk-php)
[![Twitter Follow](https://img.shields.io/twitter/follow/pepi_post.svg?style=social&label=Follow)](https://twitter.com/pepi_post)

## Official PHP Code library for [Pepipost](http://www.pepipost.com/?utm_campaign=GitHubSDK&utm_medium=GithubSDK&utm_source=GithubSDK)
This SDK contain methods for easily interacting with the Pepipost Email Sending API to send emails within few seconds.
 
We are trying to make our libraries a Community Driven. To help us building right things in proper order we would request you to help us by sharing comments, creating new [issues](https://github.com/hellovikram/pepipost-php/issues) or [pull request](https://github.com/hellovikram/pepipost-php/pulls).

## Table of Contents
* [Installation](#installation)
* [Announcements](#announcements)
* [Roadmap](#roadmap)
* [About](#about)
* [License](#license)

<a name="installation"></a>
## Installation (OS Friendly)

Inorder to make it Smooth we have Separated installation process with respective OS which will help you to go step by step without any interuption.

1. [Build SDK on Windows without any IDE.](https://github.com/hellovikram/pepipost-php/blob/feature_x/pepipost-sdk-php/windows-Installation-1.md)
2. [Build SDK on Windows/Linux with IDE.](https://github.com/hellovikram/pepipost-php/blob/feature_x/pepipost-sdk-php/windows-installation-2.md)
3. [Build SDK on Linux.](https://github.com/hellovikram/pepipost-php/blob/feature_x/pepipost-sdk-php/linux-installation.md)


## Download Basic Requirements for installation

**1. [PHP >=5.3.2](http://php.net/manual/en/install.php)**

**2. [Composer](https://getcomposer.org/download/)**

**3. CURL**

## Building SDK 

 1. Open Command prompt/ terminal. 
 
 2. Change Directory to any new directory (Make directory test-- recommended).
 
 3. [Download or Clone](https://github.com/hellovikram/pepipost-php/archive/feature_x.zip) the Pepipost Repository to the new directory.
 
 4. Check php version using **```php -v```**
 
 5. Check Composer version **```composer --version```**
 
 6. Navigate to your directory where SDK is Downloaded/clone/extracted (using cd path\to\directory)
 
 7. Type **```composer install```** (this will install all the requirement needed to Run SDK -- vendor directory will be listed )
 
 8. Make file in same directory **```test.php```**
 
 9. Copy and Paste the [simpleUsage.md](https://github.com/hellovikram/pepipost-php/blob/feature_x/pepipost-sdk-php/simpleUsage.md) file or [sampleExample](https://github.com/hellovikram/pepipost-php/blob/feature_x/pepipost-sdk-php/README.md#sample-usage) below of the Readme.md file in test.php
 
 10. Grab your apiKey and SendingDomain from panel 
  
  **```apikey```** will be available from **```login to pepipost -> settings -> integration```**
  
  **```Sending Domain```** will be available from **```login to pepiost -> settings -> Sending Domains ```**

```
  *note :: only Active Domains are allowed * 
```

 11. Make neccessary Changes in Script (apikey and Sending Domain -- mandatory changes).
 
 Change your **```$apiKey = 'api-XX-key-XX-here'```** to **```$apiKey = 'api-key-from-panel';```**
 
 Similarly Change your Sending Domain from **```$body->from->fromEmail = 'admin@myfirsttest.com';```** to **```$body->from->fromEmail = 'admin@your-active-domain-from-panel';```**


## Initialization

### How to initialize Pepipost Api Client

API client can be initialized as following.

```php

  $client = new PepipostAPILib\PepipostAPIClient();
  
```

## Class Reference

### <a name="list_of_controllers"></a>List of Controllers

* [EmailController](#email_controller)

### <a name="email_controller"></a>![Class: ](https://apidocs.io/img/class.png ".EmailController") EmailController

### Get singleton instance

The singleton instance of the ``` EmailController ``` class can be accessed from the API Client.

```php
$email = $client->getEmail();
```

### <a name="create_send_email"></a>![Method: ](https://apidocs.io/img/method.png ".EmailController.createSendEmail") createSendEmail

> *Tags:*  ``` Skips Authentication ``` 

> This Endpoint sends emails with the credentials passed.


```php
function createSendEmail(
        $apiKey = null,
        $body = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| apiKey |  ``` Optional ```  | Generated header parameter. Example value ='5ce7096ed4bf2b39dfa932ff5fa84ed9ed8' |
| body |  ``` Optional ```  | The body passed will be json format. |


## Sample Usage

```php
<?php
require_once "vendor/autoload.php";
$client = new PepipostAPILib\PepipostAPIClient();
$emailController = $client->getEmail();

// Your Pepipost API Key
$apiKey = 'api-XX-key-XX-here'; #add apikey from panel here

$body = new PepipostAPILib\Models\EmailBody();

// List of Email Recipients
$body->personalizations = array();
$body->personalizations[0] = new PepipostAPILib\Models\Personalizations;
$body->personalizations[0]->recipient = 'Youremailid@XXX.com';               #To/Recipient email address

// Email Header
$body->from = new PepipostAPILib\Models\From;
$body->from->fromEmail = 'admin@myfirsttest.com';   #Sender Domain. Note: The sender domain should be verified and active under your Pepipost account.
$body->from->fromName = 'Test Admin';       #Sender/From name

//Email Body Content
$body->subject = 'Pepipost mail through php sdk';               #Subject of email
$body->content = '<html><body>Hello, Email testing is successful. <br> Hope you enjoyed this integration. <br></html>'; #HTML content which need to be send in the mail body

// Email Settings
$body->settings = new PepipostAPILib\Models\Settings;
$body->settings->clicktrack = 1;    #clicktrack for emails enable=1 | disable=0
$body->settings->opentrack = 1;     #opentrack for emails enable=1 | disable=0
$body->settings->unsubscribe = 1;   #unsubscribe for emails enable=1 | disable=0

$response = $emailController->createSendEmail($apiKey,$body);   #function sends email
print_r(json_encode($response));
?>
```


[Back to List of Controllers](#list_of_controllers)

<a name="announcements"></a>
# Announcements

v3 has been released! Please see the [release notes](https://github.com/pepipost/pepipost-php/releases/tag/v3.0.0) for details.

All updates to this library are documented in our [CHANGELOG](https://github.com/pepipost/pepipost-php/blob/master/CHANGELOG.md) and [releases](https://github.com/pepipost/pepipost-php/releases). For any queries, feel free to reach out us at dx@pepipost.com

<a name="roadmap"></a>
## Roadmap

If you are interested in the future direction of this project, please take a look at our open [issues](https://github.com/pepipost/pepipost-php/issues) and [pull requests](https://github.com/pepipost/pepipost-php/pulls). We would love to hear your feedback.

<a name="about"></a>
## About
pepipost-php library is guided and supported by the Pepipost Developer Experience Team.
This pepipost-php library is maintained and funded by Pepipost Ltd. The names and logos for pepipost-php are trademarks of Pepipost Ltd.

<a name="license"></a>
## License
This code library was semi-automatically generated by APIMATIC v2.0 and licensed under The MIT License (MIT). 
