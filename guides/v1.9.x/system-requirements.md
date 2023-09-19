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
* MySQL 5.6+ (8.0+ recommended) or MariaDB

### PHP

OpenMage LTS 1.9.x
* PHP 7.4+ (PHP 8.0 is supported, PHP 8.1 supported but some warnings may be shown/logged, PHP 8.2 is usable but still being tested)

* If using php 7.2+ then mcrypt needs to be disabled in php.ini or pecl to fallback on mcryptcompat and phpseclib. mcrypt is deprecated from 7.2+ onwards.

* PHP extension intl since 1.9.4.19 & 20.0.17

### SSL
* Magento is SSL ready and for HTTPS it just needs a valid security certificate 
* Self-signed SSL certificates are not supported
* OpenSSl recommended

### Patching 
* Command patch 2.7+ (or gpatch on MacOS/HomeBrew) since 1.9.5.0 & 20.1.0

### Optional 
* Redis 5.x, 6.x and 7.0.x are supported