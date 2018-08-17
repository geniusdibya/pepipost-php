# SDK on windows without IDE

The Mentioned Steps below will help you in integrating Pepipost SDK with Windows Server which doesn't have any IDE
Before starting we would request you to whitelist our domain ```api.pepipost.com``` with ```port 443/80```  

### Installation Step 

This code has dependencies over external libraries like UniRest.
Dependencies are listed in ```composer.json``` file that comes with SDK.

We are trying to help you with the simpliest way of installation we can let us know if problem arises while installtion through ![issues](https://github.com/hellovikram/pepipost-php/issues) or ![pull requests](https://github.com/hellovikram/pepipost-php/pulls).

1. ![Install Xampp](https://www.apachefriends.org/download.html)

2. ![Install composer](https://getcomposer.org/doc/00-intro.md#installation-windows)
![imgcomposer](http://app1.falconide.com/integration_imgs/windows_without_IDE/1.png)

  Step a :: As soon as you download composer.exe file from the above link pop will appear below
  
  ![installation](http://app1.falconide.com/integration_imgs/windows_without_IDE/2.png)
  
  Step b :: Installation directory will be shown at the below
  
  ![installation2](http://app1.falconide.com/integration_imgs/windows_without_IDE/3.png)
  
  Step c :: Proxy Url if you want any, we don't want such for now so keeping blank
  
  ![installation3](http://app1.falconide.com/integration_imgs/windows_without_IDE/4.png)
  
  Step d :: last Process will prompt for Ready to install 
  
  ![installation4](http://app1.falconide.com/integration_imgs/windows_without_IDE/5.png)
  
  Step e :: Downloading Procedure
  
  ![installation5](http://app1.falconide.com/integration_imgs/windows_without_IDE/6.png)
  
  Step f :: Last Legacy installation Finish (Successfully installed)
  
  ![installtion6](http://app1.falconide.com/integration_imgs/windows_without_IDE/7.png)
  
3.  Open CMD. (command prompt) 

 ![cmd](http://app1.falconide.com/integration_imgs/windows_without_IDE/8.png) 
 
4.  Check Composer version on CMD ```Composer --version``` 

 ![version]()

5.  Download zip from ![Pepipost Repository](https://github.com/pepipost/pepipost-sdk-php/archive/master.zip)

![dwnimg](http://app1.falconide.com/integration_imgs/windows_without_IDE/9.png)

6.  if you have git installed please clone the ![same here](https://github.com/pepipost/pepipost-sdk-php.git)

7.  unzip the downloaded zip to Fresh Directory at any location of your choice. (we will assume Dev has Directory at location Desktop)
8.  

