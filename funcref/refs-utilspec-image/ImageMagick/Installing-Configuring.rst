安装配置
==========

需求
-------------------

Installation requirements on Windows
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Version information does not differ from that above. There are binaries available from http://www.imagemagick.org/ so that you can load this extension on Windows without need for a compiler.

Installation requirements on other platforms
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

PHP >= 5.1.3 and ImageMagick >= 6.2.4 is required. The amount of formats supported is by Imagick is entirely dependent upon the amount of formats supported by your ImageMagick installation. For example, Imagemagick requires ghostscript to conduct PDF operations.

安装
-------------------


This » PECL extension is not bundled with PHP.

Information for installing this PECL extension may be found in the manual chapter titled Installation of PECL extensions. Additional information such as new releases, downloads, source files, maintainer information, and a CHANGELOG, can be located here: » http://pecl.php.net/package/imagick.

Note: The official name of this extension is imagick.

A DLL for this PECL extension is currently unavailable. See also the building on Windows section.

.. code-block:: bash

 #yum install ImageMagick*
 #pecl install imagick 

sometimes you may have ask to install gcc compiler. if so execute 

.. code-block:: bash

 #yum install gcc*

added the extension on php.ini

.. code-block:: bash

 #echo "extension=imagick.so" >> /etc/php.ini
 #service httpd restart


配置
-------------------

The behaviour of these functions is affected by settings in php.ini.

Imagick configuration options
Name	Default	Changeable	Changelog
imagick.locale_fix	FALSE	PHP_INI_ALL	Available since Imagick 2.1.0
imagick.progress_monitor	FALSE	PHP_INI_SYSTEM	Available since Imagick 2.2.2 For further details and definitions of the PHP_INI_* modes, see the Where a configuration setting may be set.
Here's a short explanation of the configuration directives.

imagick.locale_fix boolean
Fixes a drawing bug with locales that use ',' as float separators.

imagick.progress_monitor boolean
Used to enable the image progress monitor.

资源类型
-----------------
