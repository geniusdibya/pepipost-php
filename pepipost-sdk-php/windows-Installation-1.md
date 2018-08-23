# Steps to install Pepipost PHP Code Library on windows without IDE

Dedicated to Terminal Lovers who ❤️ to code on terminal.

Below steps will help you in integrating this PHP code library with Windows machine which doesn't have any IDE. 

> Optional Note: This library will be sending HTTP calls to Pepipost server and hence if you're running any firewalls then please whitelist the API base URL ```api.pepipost.com``` with ```port 443/80```

### Installation Steps

This code has dependencies over external libraries like UniRest. All dependencies are listed in the file ```composer.json```.

We are trying to cover each of the steps in this installation, which might make this doc a little lengther but the objective is to help you with the simpliest way of installation. 

While Pepipost is defintely leading this library, but we want this to be more community driven. Your help is needed to realize this goal and to make sure we are building the right things in the right order. We ask that you create ![issues](https://github.com/hellovikram/pepipost-php/issues) and ![pull requests](https://github.com/hellovikram/pepipost-php/pulls) or simply upvote or comment on existing issues or pull requests to keep everyone updated.

We appreciate your continued support, thank you!

Step 1. Install [XAMPP](https://www.apachefriends.org/download.html)

Step 2. Install [COMPOSER](https://getcomposer.org/doc/00-intro.md#installation-windows)
![imgcomposer](http://app1.falconide.com/integration_imgs/windows_without_IDE/1.png)
  2.1. As soon as you download composer.exe file from the above link pop will appear below:
  ![installation](http://app1.falconide.com/integration_imgs/windows_without_IDE/2.png)
  
  2.2. Installation directory will be shown at the below:
  ![installation2](http://app1.falconide.com/integration_imgs/windows_without_IDE/3.png)
  
  2.3. Proxy URL if you want any, we don't want such for now so keeping blank
  
  ![installation3](http://app1.falconide.com/integration_imgs/windows_without_IDE/4.png)
  
  Step d :: last Process will prompt for Ready to install 
  
  ![installation4](http://app1.falconide.com/integration_imgs/windows_without_IDE/5.png)
  
  Step e :: Downloading Procedure
  
  ![installation5](http://app1.falconide.com/integration_imgs/windows_without_IDE/6.png)
  
  Step f :: Last Legacy installation Finish (Successfully installed)
  
  ![installtion6](http://app1.falconide.com/integration_imgs/windows_without_IDE/7.png)
  
3.  Open CMD &  Check Composer version using ```Composer --version``` (command prompt) 

 ![cmd](http://app1.falconide.com/integration_imgs/windows_without_IDE/8.png) 
 

4.  Download zip or clone git repo from ![Pepipost Repository](https://github.com/pepipost/pepipost-sdk-php/archive/master.zip)

![dwnimg](http://app1.falconide.com/integration_imgs/windows_without_IDE/9.png)

6.  unzip the downloaded zip to Fresh Directory at any location of your choice. (we will assume Dev has Directory at location Desktop)

![extract](http://app1.falconide.com/integration_imgs/windows_without_IDE/10.png)


8. copy the path from address bar of window where you have unzipped the repository

![unzipp](http://app1.falconide.com/integration_imgs/windows_without_IDE/11.png)

9. Paste in CMD with ```cd copied\PATH\to\Directory``` 

![path](http://app1.falconide.com/integration_imgs/windows_without_IDE/12.png)

10. Once you had copied & successfully migrated to Unzipped Path 
    
   install composer using ```composer install``` these will install all the requirement for Building SDK

 ![composer](http://app1.falconide.com/integration_imgs/windows_without_IDE/14.png)

11. Download CURL (https://curl.haxx.se/docs/caextract.html) for windows

    move **.pem** from downloads directory to the unzipped SDK folder.
  
  ![downloadcurl](http://app1.falconide.com/integration_imgs/windows_without_IDE/15.png)
  
 12. As we have downloaded the Curl we need to add in our php.ini file 
 
     Open xampp Control panel -> config(php.ini) file shown below
     
  ![xampp](http://app1.falconide.com/integration_imgs/windows_without_IDE/16.png)
  
 13. Add line ```**curl.cainfo = "PATH_TO/cacert.pem"**``` to php.ini file
 
  ![PEm file](http://app1.falconide.com/integration_imgs/windows_without_IDE/18.png)
  
 14. Make a Sample file named **test.php** in the unzipped directory as shown below
 
  ![testfile](http://app1.falconide.com/integration_imgs/windows_without_IDE/20.png)
  
 15. Open file with notepad (for simpliest debugging would like to recommend :: notepad++ (https://notepad-plus-plus.org/download/v7.5.8.html))
   
 16. Copy and paste Simple Usage example from ![simpleUsage.php](https://github.com/hellovikram/pepipost-php/blob/feature_x/pepipost-sdk-php/simpleUsage.php) in **test.php**
 
 17. Make changes in the file (replace/add your credentials available from panel) 
  
   Step a :: Get **api_key** from Panel
             replace line ```$apiKey = 'api-XX-key-XX-here'``` in SimpleUsage with ```$apiKey = 'api-key-from-panel refer the image below'``` 
        
   ![panel](http://app1.falconide.com/integration_imgs/windows_without_IDE/22.png)
 
   ![api_key](http://app1.falconide.com/integration_imgs/windows_without_IDE/23.png)
   
   Step b :: Get **Sending Domain** from panel (should be verified/Active)
             replace ```$body->from->fromEmail = 'admin@myfirsttest.com'``` with ```$body->from->fromEmail = 'admin@domain-from-panel-refer-image-below```
             
   ![domain](http://app1.falconide.com/integration_imgs/windows_without_IDE/31.png)
    
   ![sendingdomain](http://app1.falconide.com/integration_imgs/windows_without_IDE/30.png)
 
 18. Ready to Go..! 
 
   Save you File and open CMD -> cd Path\to\Unzipped\directory
   
   Check Syntax by **C:\xampp\php\php.exe -l Path\to\Unzipped\directory\test.php**
   
   **Syntax ok** will be prompted if everything is correct in your test.php file
   
   Send your first mail now with **C:\xampp\php\php.exe Path\to\Unzipped\directory\test.php**
   
   ![success](http://app1.falconide.com/integration_imgs/windows_without_IDE/26.png)
   
 19.Check your Email Inbox (please **mark as not spam** if it is found in spam)
 
   ![check1](http://app1.falconide.com/integration_imgs/windows_without_IDE/27.png)
   
   ![check2](http://app1.falconide.com/integration_imgs/windows_without_IDE/28.png)
   
   
 20. Success :: You have Successfully Integrated Pepipost :smiley: . 
 

   
   
   
 
    
