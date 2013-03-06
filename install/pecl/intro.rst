PECL 安装介绍
====================


`» PECL <http://pecl.php.net/>`_ 是通过 `» PEAR <http://pear.php.net/>`_ 打包系统来的 PHP 扩展库仓库，本章内容示范了怎样取得并安装 PECL 扩展。

以下指南中假定 **/your/phpsrcdir/** 是 PHP 源程序的路径，**extname** 是 PECL 扩展库的名字。自己根据实际情况调整。此外还假定用户熟悉 `» pear 命令 <http://pear.php.net/manual/en/guide.users.commandline.cli.php>`_。 PEAR 手册里 **pear** 命令的信息同样适用于 **pecl**。

要使用共享扩展库，必须经过编译，安装，然后加载。以下说明的方法提供了怎样编译和安装扩展库的各种指导，但并不会自动加载它们。可以通过将其包括在 php.ini 中用 extension PHP 指令加载，或者 用 dl() 函数。

当编译 PHP 模块时，拥有各种工具（autoconf，automake，libtool 等）的已知好使的版本很重要。所需工具和所需版本的详情见» 匿名 :doc:`Git 说明</git>`。
