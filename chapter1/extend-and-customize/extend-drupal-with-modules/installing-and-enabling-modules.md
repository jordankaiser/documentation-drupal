# Installing and Enabling Modules

There are two ways of installing and enabling Drupal modules. One is through the Drupal interface and the other is to manually place the files into the proper installation directory.

Modules are stored in _sites &gt; all &gt; modules_. You'll see a modules folder at the root of you site as well. This is only for core modules and should be modified.

## Installing a modules through the Admin interface

First make sure _Update Manager _ is turned on under the _Extend_ section of the Drupal CMS. This module allows you to install other modules through the admin interface is also helps keep you installed modules up to date.

Also this is a good visual representation of how modular drupal is. Practically all of the functionality is pulled in via a module listed on the _Extend_ page.

The service I'm using to host my test Drupal site doesn't allow for Module installation in the admin interface or through SFTP so the rest of this is untested.

* To install a new modules click the \_Install \_button on the \_Extend \_page.
* You'll have two options, Install from a URL or Upload a module.
  * Install from URL.
    * Once you find a drupal module with the module ecosystem you can right click on it's tar.gz, copy the link and paste it here.
    * Click install and drupal will install it.
    * Note that this method will note automatically download or install any dependencies.

## Install a module manually

To install a module manually:

* Download the tar.gz.
* Upload it to the correct directory

## Enable the module

Whether you install in manually or through the admin interface you'll need to enable the module once installed.

* Go to _Extend_ and find the module you wish to enable.
* Click the checkbox next to it.
* Click save
* If Drupal detects any module dependencies it will try and turn them on as well. It won't download them but if there are already there it will turn them on.



