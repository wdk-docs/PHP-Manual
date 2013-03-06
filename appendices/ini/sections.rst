配置段列表
==========

This list includes the php.ini sections you can set to configure your PHP setup on a per Host or Path basis. These sections are optional.

These sections don't directly affect PHP. They are used to group other php.ini directives together and to get them to act upon a particular host or on a particular path.

These sections are used only in CGI/FastCGI mode and they can not set extension and zend_extension directives.

配置段

============== =============== ====================
名字            可修改范围      更新日志
============== =============== ====================
[HOST=]        PHP_INI_SYSTEM  在 PHP 5.3.0 时增加。
[PATH=]        PHP_INI_SYSTEM  在 PHP 5.3.0 时增加。
============== =============== ====================

这是配置指令的简短说明。

[HOST=<host>]
This section allows you to define a set of php.ini directives that will take effect on the named host.

Example #1 Activate full on-screen error reporting for dev. domain

.. code-block:: ini

 [HOST=dev.site.com]
 error_reporting = E_ALL
 display_errors = On
 [PATH=<path>]

This section allows you to define a set of php.ini directives that will take effect when a script runs from the named path.

Example #2 Add security script for protected areas

.. code-block:: ini

 [PATH=/home/site/public/secure]
 auto_prepend_file=security.php
