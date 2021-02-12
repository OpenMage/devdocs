---
layout: full-width
group: system-requirements
---
System Requirements
===============================

System Requirements for OpenMage LTS (Magento 1 Fork)
----------------------------------
### Operating System
Linux x86-64

### Web Server
* Apache 2.x
* Nginx 1.8.x

### Database
OpenMage LTS 1.9.x and later:
* MySQL 5.7 (Oracle, Percona, MariaDB)

### PHP

OpenMage LTS 1.9.x
* PHP 7.0+ (PHP 7.3 and OpenSSL extension strongly recommended)

* If using php 7.2+ then mcrypt needs to be disabled in php.ini or pecl to fallback on mcryptcompat and phpseclib. mcrypt is deprecated from 7.2+ onwards.

### SSL
* Magento is SSL ready and for HTTPS it just needs a valid security certificate 
* Self-signed SSL certificates are not supported
* OpenSSl recommended

### Other
--------------------------------------
To find individual system requirements for the Magento 2.3.x, and 2.4.x releases, see the following pages:

* [Magento 2.4.x system requirements](https://devdocs.magento.com/guides/v2.4/install/system-requirements.html)
* [Magento 2.3.x system requirements](https://devdocs.magento.com/guides/v2.3/install/system-requirements.html)

