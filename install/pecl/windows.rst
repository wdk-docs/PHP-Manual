在 Windows 上安装 PHP 扩展
============================


在 Windows 上有两种加载 PHP 扩展的方式：把扩展编译进 PHP，或者加载 DLL。加载预编译的扩展是更简单更被推荐的方式。

To load an extension, you need to have it available as a ".dll" file on your system. All the extensions are automatically and periodically compiled by the PHP Group (see next section for the download).

To compile an extension into PHP, please refer to building from source documentation.

To compile a standalone extension (aka a DLL file), please refer to building from source documentation. If the DLL file is available neither with your PHP distribution nor in PECL, you may have to compile it before you can start using the extension.

哪里找扩展?
-----------

PHP extensions are usually called "php_*.dll" (where the star represents the name of the extension) and they are located under the "PHP\ext" ("PHP\extensions" in PHP 4) folder.

PHP ships with the extensions most useful to the majority of developers. They are called "core" extensions.

However, if you need functionality not provided by any core extension, you may still be able to find one in PECL. The PHP Extension Community Library (PECL) is a repository for PHP Extensions, providing a directory of all known extensions and hosting facilities for downloading and development of PHP extensions.

If you have developed an extension for your own uses, you might want to think about hosting it on PECL so that others with the same needs can benefit from your time. A nice side effect is that you give them a good chance to give you feedback, (hopefully) thanks, bug reports and even fixes/patches. Before you submit your extension for hosting on PECL, please read http://pecl.php.net/package-new.php.

下载哪个扩展?
--------------

Many times, you will find several versions of each DLL:

Different version numbers (at least the first two numbers should match)
Different thread safety settings
Different processor architecture (x86, x64, ...)
Different debugging settings
etc.
You should keep in mind that your extension settings should match all the settings of the PHP executable you are using. The following PHP script will tell you all about your PHP settings:

Example #1 phpinfo() call
<?php
phpinfo();
?>
Or from the command line, run:

drive:\\path\to\php\executable\php.exe -i

载入一个扩展
-----------------

最常见的方式是在 php.ini 配置文件里包含一个 PHP 扩展。 请注意很多扩展已经在 php.ini 里了，你需要的仅仅是移除分号来激活它们。

;extension=php_extname.dll
extension=php_extname.dll
However, some web servers are confusing because they do not use the php.ini located alongside your PHP executable. To find out where your actual php.ini resides, look for its path in phpinfo():

Configuration File (php.ini) Path  C:\WINDOWS
Loaded Configuration File   C:\Program Files\PHP\5.2\php.ini
After activating an extension, save php.ini, restart the web server and check phpinfo() again. The new extension should now have its own section.

Resolving problems
---------------------

If the extension does not appear in phpinfo(), you should check your logs to learn where the problem comes from.

If you are using PHP from the command line (CLI), the extension loading error can be read directly on screen.

If you are using PHP with a web server, the location and format of the logs vary depending on your software. Please read your web server documentation to locate the logs, as it does not have anything to do with PHP itself.

Common problems are the location of the DLL, the value of the " extension_dir" setting inside php.ini and compile-time setting mismatches.

If the problem lies in a compile-time setting mismatch, you probably didn't download the right DLL. Try downloading again the extension with the right settings. Again, phpinfo() can be of great help.
