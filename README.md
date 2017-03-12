BC Kernel Module Override
===================

THis extension is a simple eZ Publish Platform (Legacy) kernel override extension which overrides the default ezmodule class to provide a simple feature it allows extension based module views to override default kernel module views. Great for advanced developers!

With this kernel class override installed and enabled you can override any default kernel module and kernel module views.

This is helpful and useful for overriding default modules like the user/login module view or other module views like the information collation system or any other kernel module you desire.


Version
=======

* The current version of BC Kernel Module Override is 0.1.1

* Last Major update: March 12, 2017


Copyright
=========

* BC Kernel Module Override is copyright 1999 - 2017 Brookins Consulting and eZ Systems AS

* See: [COPYRIGHT.md](COPYRIGHT.md) for more information on the terms of the copyright and license


License
=======

BC Kernel Module Override is licensed under the GNU General Public License.

The complete license agreement is included in the [LICENSE](LICENSE.md) file.

BC Kernel Module Override is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 2 of the License or at your
option a later version.

BC Kernel Module Override is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

The GNU GPL gives you the right to use, modify and redistribute
BC Kernel Module Override under certain conditions. The GNU GPL license
is distributed with the software, see the file LICENSE.

It is also available at [http://www.gnu.org/licenses/gpl.txt](http://www.gnu.org/licenses/gpl.txt)

You should have received a copy of the GNU General Public License
along with BC Kernel Module Override in LICENSE.

If not, see [http://www.gnu.org/licenses/](http://www.gnu.org/licenses/).

Using BC Kernel Module Override under the terms of the GNU GPL is free (as in freedom).

For more information or questions please contact: license@brookinsconsulting.com


Requirements
============

The following requirements exists for using BC Kernel Module Override extension:


### eZ Publish version

* Make sure you use eZ Publish version 4.x (required) or higher.

* Designed and tested with eZ Publish Community Project 2014.11


### PHP version

* Make sure you have PHP 5.x or higher.


Features
========

This solution provides the following features:

* Kernel Module Class Override Class: eZModule


### Dependencies

* This solution depends on eZ Publish Legacy and kernel class overrides enabled in config.php


### Kernel class override

This solution overrides the following kernel class:

* PHP Class : `eZModule` - Found by default at: `lib/ezutils/classes/ezmodule.php`

This solution provides the following kernel class override:

* PHP Class : `eZModule` - Found by at: `extension/bckernelmoduleoverride/classes/kerneloverride/v2014.11.07/lib/ezutils/classes/ezmodule.php`

**Note**: This solution requires only one legacy kernel class override of a class that is very stable and not subject to much change (if at all) per release (which is important for maintainability). The class has not been modified or [needed a bugfix since early 2015](https://github.com/ezsystems/ezpublish-legacy/blob/master/lib/ezutils/classes/ezmodule.php).


Installation
============

### Bundle Installation via Composer

Run the following command from your project root to install the bundle:

    bash$ composer require brookinsconsulting/bckernelmoduleoverride dev-master;


### Extension Activation

Optional. Activate this extension by adding the following to your `settings/override/site.ini.append.php`:

    [ExtensionSettings]
    # <snip existing active extensions list />
    ActiveExtensions[]=bckernelmoduleoverride

Kernel class override extensions are **not** activated via ini settings. Normal site.ini extension activation settings are not required to use this extension and it's solution.


### Enable eZ Publish Kernel Overrides

Kernel class overrides are only able to be used if you add the following to your eZ Publish Legacy config.php configuration file.

    cp -va config.php-RECOMMENDED config.php;
    # Edit config.php to set 'EZP_AUTOLOAD_ALLOW_KERNEL_OVERRIDE' to true. It should look like this:
    define( 'EZP_AUTOLOAD_ALLOW_KERNEL_OVERRIDE', true );


### Regenerate kernel class override autoloads

Regenerate kernel class override autoloads (Required).

    php ./bin/php/ezpgenerateautoloads.php --kernel-override;


### Clear the caches

Optional. Clear eZ Publish Platform / eZ Publish Legacy caches (Required).

    php ./bin/php/ezcache.php --clear-all;


Usage
=====

The solution is configured to work virtually by default once properly installed.

Note: If you have any other extension modules which the module name is the same of a default module the extension module will now override the default module by default. This could be a concern so check your modules before deploying to production / live.

With this kernel class override installed and enabled you can override any default kernel module and kernel module views.

This is helpful and useful for overriding default modules like the user/login module view or other module views like the information collation system or any other kernel module you desire.

Troubleshooting
===============

### Read the FAQ

Some problems are more common than others. The most common ones are listed in the the [doc/FAQ.md](doc/FAQ.md)


### Support

If you have find any problems not handled by this document or the FAQ you can contact Brookins Consulting through the support system: [http://brookinsconsulting.com/contact](http://brookinsconsulting.com/contact)

