Git访问
==============

If you wish to get the latest PHP source tree, you can obtain it through Git. You should be warned that the Git version is a development version, and as such, is often unstable, and may not even compile properly. The advantage of using Git, though, is that you can get the latest fixes and updates, without having to wait for the official releases.

PHP uses an advanced configuration system that requires you to have the following tools. re2c is only necessary for developers and can be found here. All other utilities can be obtained from the GNU FTP site.

autoconf: 2.13 (2.59+ for PHP 5.4+)
automake: 1.4+
libtool: 1.4.x+ (except 1.4.2)
bison: 1.28, 1.35, 1.75, 2.0 or higher
flex (PHP 5.2 and earlier): 2.5.4 (not higher)
re2c: 0.13.4+
If you're experiencing problems, see also the section on buildconf failures.

通过Git使用PHP的步骤
---------------------------------

You can retrieve the PHP source code from our GitHub mirror with this command: 

git clone https://github.com/php/php-src.git 

Alternatively, you can retrieve the source code from git.php.net with this command: 

git clone http://git.php.net/repository/php-src.git 

Make sure you're in the right directory to work on PHP: 

cd php-src 

You can then check out the branch you want to build: 

PHP 5.3: git checkout PHP-5.3 
PHP 5.4: git checkout PHP-5.4 
PHP HEAD: git checkout master 

Note that certain combinations of autoconf, automake and libtool may not work when used together. See below for details.
Also, certain versions of autoconf may generate warnings of AC_PROG_CPP called before AC_PROG_CC. These messages can usually be ignored.

Run ./buildconf to generate the configure script. This may take several moments.
From this point onwards, installation is similar to the installation of one of the official packages with one main difference – you may need bison 1.28 or later and flex 2.5.4 (PHP 5.2 and earlier) or re2c 0.13.4+ or later (PHP 5.3 and later) to compile, because the pre-generated scanner and parser files may not be included in Git.
There are many other things, such as the XML source code for the documentation, available via Git. See the web-based view of the Git server to see what is available.

The PHP Wiki has a useful Git FAQ, which provides useful tips and cheatsheets for using the PHP Git repository, and if you want to become involved in developing PHP, the Git Workflow page is also likely to be of interest.

PHP 手册
--------------

The PHP manual is still currently hosted on SVN, although it will be migrated to Git in the near future. To checkout the latest English version of the PHP manual:
svn checkout https://svn.php.net/repository/phpdoc/modules/doc-en ./phpdoc-en 

You can also check the SVN FAQ on the wiki.

autoconf, automake 和 libtool 信息
-----------------------------------------------

There seem to be problems with libtool 1.4.2. It is suggested that you use libtool 1.4, along with autoconf 2.13 and automake 1.4. You should also ensure that autoconf, automake and libtool are installed in the same directory. libtool 1.5 will not work.

The following combinations are known to work with PHP 5.3 and below:

autoconf 2.13, automake 1.4 and libtool 1.4.3
autoconf 2.13, automake 1.5 and libtool 1.4.3
If you have multiple versions of autoconf installed on your computer, as is common for many UNIXes, you can set the PHP_AUTOCONF and PHP_AUTOHEADER variables when running buildconf to indicate which versions it should use e.g.:
PHP_AUTOCONF=autoconf213 PHP_AUTOHEADER=autoheader213 ./buildconf

Zend/zend_language_scanner.c: 没有这个文件或目录
----------------------------------------------------------

PHP only supports flex 2.5.4, not later versions as they broke backwards compatibility. Please note that PHP 5.3 and later do not require flex at all.
