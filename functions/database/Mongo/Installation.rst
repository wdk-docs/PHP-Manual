安装
====

The MongoDB PHP driver should work on nearly any system: Windows, Mac OS X, Unix, and Linux; little- and big-endian machines; 32- and 64-bit machines; PHP 5.2, 5.3, 5.4 and 5.5.

此 » PECL 扩展未与 PHP 捆绑。

.. contents:: 安装:
   :backlinks: none
   :local:

手动安装
--------------------

For driver developers and people interested in the latest bugfixes, you can compile the driver from the latest source code on » Github. Go to Github and click the "download" button. Then run:

.. code-block: bash

 $ tar zxvf mongodb-mongodb-php-driver-<commit_id>.tar.gz
 $ cd mongodb-mongodb-php-driver-<commit_id>
 $ phpize
 $ ./configure
 $ make all
 $ sudo make install

Make the following changes to php.ini:

Make sure the extension_dir variable is pointing to the directory containing mongo.so. The build will display where it is installing the PHP driver with output that looks something like:


Installing '/usr/lib/php/extensions/no-debug-non-zts-20060613/mongo.so'

Make sure that it is the same as the PHP extension directory by runnning:

.. code-block: bash

 $ php -i | grep extension_dir
   extension_dir => /usr/lib/php/extensions/no-debug-non-zts-20060613 =>
                    /usr/lib/php/extensions/no-debug-non-zts-20060613

If it's not, change the extension_dir in php.ini or move mongo.so.
To load the extension on PHP startup, add a line:

.. code-block: ini

 extension=mongo.so

在*NIX上安装
-------------------------

Run:

.. code-block: bash

 $ sudo pecl install mongo

If you are using CentOS or Redhat, you may wish to install from an » RPM.

Add the following line to your php.ini file:

.. code-block: ini

   extension=mongo.so

If pecl runs out of memory while installing, make sure memory_limit in php.ini is set to at least 128MB.

在Windows上安装
-----------------------

Precompiled binaries for each release are available from » Github for a variety of combinations of versions, thread safety, and VC libraries. Unzip the archive and put php_mongo.dll in your PHP extension directory ("ext" by default).

Add the following line to your php.ini file:

.. code-block: ini

   extension=php_mongo.dll

OS X
-------

If your system is unable to find autoconf, you'll need to install Xcode (available on your installation DVD or as a free download from the Apple website).

If you are using XAMPP, you may be able to compile the driver with the following command:

.. code-block: bash

 sudo /Applications/XAMPP/xamppfiles/bin/pecl install mongo

If you are using MAMP (or XAMPP and the above command does not work), precompiled binaries are available from » Github (download the latest one with "osx" in the name that matches your version of PHP). Extract mongo.so from the archive and add it to MAMP or XAMPP's extension directory. Add

.. code-block: ini

 extension=mongo.so

to the php.ini file being used and restart the server.

Gentoo
----------

Gentoo has a package for the PHP driver called dev-php5/mongo, which can be installed with:

.. code-block: bash

 $ sudo emerge -va dev-php5/mongo

If you use PECL, you may get an error that libtool is the wrong version. Compiling from source you'll need to run aclocal and autoconf.

.. code-block: bash

 $ phpize
 $ aclocal 
 $ autoconf 
 $ ./configure
 $ make
 $ sudo make install

Red Hat
----------

This includes Fedora and CentOS.

The default Apache settings on these systems do not let requests make network connections, meaning that the driver will get "Permission denied" errors when it tries to connect to the database. If you run into this, try running:

.. code-block: bash

$ /usr/sbin/setsebool -P httpd_can_network_connect 1 

Then restart Apache. (This issue has also occurred with SELinux.)

第三方安装说明
------------------

A number of people have created excellent tutorials on installing the PHP driver.

»  PHP 5.3.1 with Xdebug, MongoDB and Lithium on Ubuntu 9.10 / Apache 2.2

An excellent video that takes you step-by-step through installing Apache, PHP, Xdebug, MongoDB, and Lithium by Jon Adams.

»  Installing MongoDB and the PHP driver on Ubuntu 9.04

Spanish article by Javier Aranda (»  English translation).

»  OS X: Installing MongoDB and the PHP Mongo Driver

By Matt Butcher.


