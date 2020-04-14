# laravel
Laravel framework

* **Step1: install XAMPP**
  - URL: https://www.apachefriends.org/index.html
  - Install XAMPP from file download (NEXT...)
* **Step2: config XAMPP**
  - Apache ***httpd.conf***
     - Change port 80 to 3000
     - Save
  - Apache ***httpd-ssl.conf***
     - Change port 443 to 1441
     - Save
  - Change ***Config***
     - From XAMPP > Click ***Config*** > Click ***Service and Port Settings***
     - Change ***Main Port*** to 3000
     - Change ***SSL Port*** to 1441
     - Save > Save
  - Start ***Apache*** and ***MySQL***
* **Step3: check web is working**
  - Open ***localhost:3000*** from any browser.
* **Step4: install IDE**
  - Install ***Visual Studio Code*** or any IDE
* **Step5: download Composer**
  - From: https://getcomposer.org
  - Download and install
  - Composer will download package from website: https://packagist.org/
  - From cmd check Composer version: ```> Composer --version```
* **Step5: download and install Git**
  - Download from website: https://git-scm.com
  - And install
* **Step6: Creating a Laravel project**
  - Open ```Git``` from folder ***XAMPP/htdocs***
  - Command create project: ```composer create-project --prefer-dist laravel/laravel cms 5.2``` 
    - 5.2 is laravel version
    - Remove 5.2 if you want to create lastest laravel version
    - If error, from folder ***cms*** run cmd: ```composer update --no-scripts```
  - Project cms created in folder **htdocs**
* **Step7: Virtual host**
  - Change port 3000 to 80 and port 1441 to 443 from **Step2**
  - Stop and start Apache and MySQL
  - Open file ***httpd-vhosts.conf*** from folder ***xampp/apache/conf/extra*** and add VirtualHost to this file.
  ```
  <VirtualHost *:80>
	DocumentRoot "D:/xampp/htdocs"
	ServerName localhost
  </VirtualHost>
  <VirtualHost *:80>
	DocumentRoot "D:/xampp/htdocs/cms/public"
	ServerName cms.lan
  </VirtualHost>
  ```
  - Open file ***hosts*** from folder ***Windows/system32/drivers/etc*** and add lines below to this file
  ```
  127.0.0.1 localhost
  127.0.0.1 cms.lan
  ```
