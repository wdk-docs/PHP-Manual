Where a configuration setting may be set
===============================================

These modes determine when and where a PHP directive may or may not be set, and each directive within the manual refers to one of these modes. For example, some settings may be set within a PHP script using ini_set(), whereas others may require php.ini or httpd.conf.

For example, the output_buffering setting is PHP_INI_PERDIR therefore it may not be set using ini_set(). However, the display_errors directive is PHP_INI_ALL therefore it may be set anywhere, including with ini_set().

Definition of PHP_INI_* modes

============== ========================================================================================
Mode           Meaning
============== ========================================================================================
PHP_INI_USER   Entry can be set in user scripts (like with ini_set()) or in the Windows registry Since PHP 5.3, entry can be set in .user.ini
PHP_INI_PERDIR Entry can be set in php.ini, .htaccess or httpd.conf
PHP_INI_SYSTEM Entry can be set in php.ini or httpd.conf
PHP_INI_ALL    Entry can be set anywhere
============== ========================================================================================
