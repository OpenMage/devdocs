---
title: Apache
layout: default
group: installation-guide
---
## Important: Apache rewrites and .htaccess {#apache-help-rewrite}

This topic discusses how to enable Apache 2.4 rewrites and specify a setting for the [distributed configuration file, `.htaccess`](http://httpd.apache.org/docs/current/howto/htaccess.html){:target="_blank"}.

Magento uses server rewrites and `.htaccess` to provide directory-level instructions for Apache. The following instructions are included in all of the other sections in this topic as well.

{% collapsible Click to show Apache 2.4 instructions %}
{% include install/allowoverrides24.md %}
{% endcollapsible %}

{:.bs-callout-info}
Failure to enable these settings typically results in styles not displaying on the storefront or Admin.

## Apache required modules {#apache-required-modules}

Magento requires the following Apache modules be installed:

*  [mod_deflate.c](https://httpd.apache.org/docs/2.4/mod/mod_deflate.html)
*  [mod_expires.c](https://httpd.apache.org/docs/2.4/mod/mod_expires.html)
*  [mod_headers.c](https://httpd.apache.org/docs/2.4/mod/mod_headers.html)
*  [mod_rewrite.c](https://httpd.apache.org/docs/2.4/mod/mod_rewrite.html)
*  [mod_security.c](https://modsecurity.org)
*  [mod_ssl.c](https://httpd.apache.org/docs/2.4/mod/mod_ssl.html)

## Verify the Apache version
To verify the Apache version you're currently running, enter:

```bash
apache2 -v
```
The result should look similar to this:
```terminal
Server version: Apache/2.4.41 (Ubuntu)
Server built:   2020-08-12T19:46:17
```

*  If Apache is *not* installed, see:
   *  [Installing or upgrading Apache on Ubuntu](#install-prereq-apache-ubuntu)
   *  [Installing Apache on CentOS](#install-prereq-apache-centos)

## Installing Apache on Ubuntu {#install-prereq-apache-ubuntu-install}

{% collapsible Click to show/hide content %}
To install the default version of Apache:

1. Install Apache

   ```bash
   apt-get -y install apache2
   ```

1. Verify the installation.

   ```bash
   apache2 -v
   ```

   The result displays similar to the following:

   ```terminal
    Server version: Apache/2.4.41 (Ubuntu)
    Server built:   2020-08-12T19:46:17
 ```

{% endcollapsible %}

## Upgrading Apache on Ubuntu {#install-prereq-apache-ubuntu-upgrade}

{% collapsible Click to show/hide content %}

To upgrade to Apache 2.4:

1. Add the `ppa:ondrej` repository, which has Apache 2.4:

   ```bash
   apt-get -y update
   ```

   ```bash
   apt-add-repository ppa:ondrej/apache2
   ```

   ```bash
   apt-get -y update
   ```

1. Install Apache 2.4:

   ```bash
   apt-get install -y apache2
   ```

   {:.bs-callout-info}
   If the 'apt-get install' command fails because of unmet dependencies, consult a resource like [http://askubuntu.com](http://askubuntu.com/questions/140246/how-do-i-resolve-unmet-dependencies-after-adding-a-ppa){:target="_blank"}.

1. Verify the installation.

   ```bash
   apache2 -v
   ```

   Messages similar to the following should display:

   ```terminal
    Server version: Apache/2.4.41 (Ubuntu)
    Server built:   2020-08-12T20:46:17
   ```
{% endcollapsible %}

## Installing Apache on CentOS {#install-prereq-apache-centos}

{% collapsible Click to install Apache on CentOS %}

### Installing Apache {#apache-install-centos}

1. Install Apache 2.4 if you have not already done so.

   ```bash
   yum -y install httpd
   ```

1. Verify the installation:

   ```bash
   httpd -v
   ```

   Messages similar to the following display to confirm the installation was successful:

   ```terminal
   Server version: Apache/2.2.15 (Unix)
   Server built: Oct 16 2020 14:48:21
   ```
 {% endcollapsible %}
