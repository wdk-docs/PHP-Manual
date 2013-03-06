安装
=====

需求
-----

FPM使用libevent来管理链接和进程信号. 至少需要安装libevent-1.4.11或者以上版本.

从源代码编译
-------------

编译PHP时需要 **--enable-fpm** 配置选项来激活FPM支持

以下为FPM编译的具体配置参数（全部为可选参数）:

* --with-libevent-dir - 指定libevent的安装路径

* --with-fpm-user - 设置 FPM 运行的用户身份 (默认 - nobody).

* --with-fpm-group - 设置 FPM 运行时的用户组 (默认 - nobody).
