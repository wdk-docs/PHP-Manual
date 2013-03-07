下载 PECL 扩展库
====================

下载 PECL 扩展库有几种方法，如：

* pecl install extname 命令会自动下载扩展代码， 所以在这种情况下不需要再次下载。
* » http://pecl.php.net/ PECL 网站包括有 PHP 开发组提供的不同扩展库的信息。这里的信息包括：更新记录，版本说明，需求，以及其它信息。
* pecl download extname PECL 网站中列出的 PECL 扩展库的发行版本可以用 » pear 命令来下载和安装。也可以指明具体的修正版。
* SVN 大多数 PECL 扩展库也在 SVN 中。其 web 页面见 be seen at » http://svn.php.net/viewvc/pecl/。要直接从 SVN 中下载，用以下命令:

   .. code-block:: bash

      $ svn checkout http://svn.php.net/repository/pecl/extname/trunk extname

* Windows 下载 目前 PHP 项目没有为 Windows 下 PECL 扩展编译二进制文件。 要在 Windows 下编译 PHP，请阅读有关章节。
