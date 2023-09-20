---
group: installation-guide
title: Installation
layout: full-width
---
### Manual Install
[GitHub](https://github.com/OpenMage/magento-lts#installation)

Download the latest [release archive](https://github.com/OpenMage/magento-lts/releases) and extract it over your existing install. **Important:** you must download the ZIP file from a tagged version on the releases page, otherwise there will be missing dependencies.

### Composer

Step 1: Create a new composer project:

```bash
composer init
```

Step 2: Configure composer. **The below options are required.** You can see all options [here](https://github.com/AydinHassan/magento-core-composer-installer#configuration).

```bash
# Allow composer to apply patches to dependencies of magento-lts
composer config --json extra.enable-patching true

# Configure Magento core composer installer to use magento-lts as the Magento source package
composer config extra.magento-core-package-type magento-source

# Configure the root directory that magento-lts will be installed to, such as "pub", "htdocs", or "www"
composer config extra.magento-root-dir pub
```

Step 3: Require `magento-core-composer-installer`:

``` bash
# PHP 7
composer require "aydin-hassan/magento-core-composer-installer":"~2.0.0"

# PHP 8
composer require "aydin-hassan/magento-core-composer-installer":"^2.1.0"
```

<small>Note: be sure to select `y` if composer asks you to trust `aydin-hassan/magento-core-composer-installer`.</small>

Step 4: Require the appropriate version of `magento-lts`:

```bash
# Latest tagged v20 series release
composer require "openmage/magento-lts":"^20.0.0"

# Legacy v19 tagged release (Magento 1.9.4.x drop-in replacement supported until April 4, 2025)
composer require "openmage/magento-lts":"^19.4.0"

# Latest on "main" development branch
composer require "openmage/magento-lts":"dev-main"

# Latest on "next" development branch
composer require "openmage/magento-lts":"dev-next"
```

<small>Note: be sure to select `y` if composer asks you to trust `magento-hackathon/magento-composer-installer` or `cweagans/composer-patches`.</small>

When deploying to a production environment, it's recommended to optimize Composer's autoloader to speed up classes lookup time:

```bash
composer dump-autoload --optimize
```

### Git

If you want to contribute to the project:

```bash
git init
git remote add origin https://github.com/<YOUR GIT USERNAME>/magento-lts
git pull origin main
git remote add upstream https://github.com/OpenMage/magento-lts
git pull upstream main
git add -A && git commit
```

[More Information](http://openmage.github.io/magento-lts/install.html)

### Secure your installation

Don't use common paths like /admin for OpenMage Backend URL. Don't use the path in _robots.txt_ and keep it secret. You can change it from Backend (System / Configuration / Admin / Admin Base Url) or by editing _app/etc/local.xml_:

```xml
<config>
    <admin>
        <routers>
            <adminhtml>
                <args>
                    <frontName><![CDATA[admin]]></frontName>
                </args>
            </adminhtml>
        </routers>
    </admin>
</config>
```

Don't use common file names like api.php for OpenMage API URLs to prevent attacks. Don't use the new file name in _robots.txt_ and keep it secret with your partners. After renaming the file you must update the webserver configuration as follows:

### Apache .htaccess
```
RewriteRule ^api/rest api.php?type=rest [QSA,L]
```

### Nginx
```
rewrite ^/api/(\w+).*$ /api.php?type=$1 last;`
```