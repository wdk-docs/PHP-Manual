.user.ini files
====================================

.user.ini files

Since PHP 5.3.0, PHP includes support for .htaccess-style INI files on a per-directory basis. These files are processed only by the CGI/FastCGI SAPI. This functionality obsoletes the PECL htscanner extension. If you are using Apache, use .htaccess files for the same effect.

In addition to the main php.ini file, PHP scans for INI files in each directory, starting with the directory of the requested PHP file, and working its way up to the current document root (as set in $_SERVER['DOCUMENT_ROOT']). In case the PHP file is outside the document root, only its directory is scanned.

Only INI settings with the modes PHP_INI_PERDIR and PHP_INI_USER will be recognized in .user.ini-style INI files.

Two new INI directives, user_ini.filename and user_ini.cache_ttl control the use of user INI files.

user_ini.filename sets the name of the file PHP looks for in each directory; if set to an empty string, PHP doesn't scan at all. The default is .user.ini.

user_ini.cache_ttl controls how often user INI files are re-read. The default is 300 seconds (5 minutes).


