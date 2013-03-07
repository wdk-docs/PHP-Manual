配置文件
===========

配置文件（php.ini）在 PHP 启动时被读取。对于服务器模块版本的 PHP，仅在 web 服务器启动时读取一次。对于 CGI 和 CLI 版本，每次调用都会读取。

php.ini 的搜索路径如下（按顺序）：

* SAPI 模块所指定的位置（Apache 2 中的 PHPIniDir 指令，CGI 和 CLI 中的 -c 命令行选项，NSAPI 中的 php_ini 参数，THTTPD 中的 PHP_INI_PATH 环境变量）
* PHPRC 环境变量。Before PHP 5.2.0, this was checked after the registry key mentioned below.
* As of PHP 5.2.0, the location of the php.ini file can be set for different versions of PHP. The following registry keys are examined in order: [HKEY_LOCAL_MACHINE\SOFTWARE\PHP\x.y.z], [HKEY_LOCAL_MACHINE\SOFTWARE\PHP\x.y] and [HKEY_LOCAL_MACHINE\SOFTWARE\PHP\x], where x, y and z mean the PHP major, minor and release versions. If there is a value for IniFilePath in any of these keys, the first one found will be used as the location of the php.ini (Windows only).
* [HKEY_LOCAL_MACHINE\SOFTWARE\PHP] 内 IniFilePath 的值（Windows 注册表位置）。
* 当前工作目录（对于 CLI）
* web 服务器目录（对于 SAPI 模块）或 PHP 所在目录（Windows 下其它情况）
* Windows 目录（C:\windows 或 C:\winnt），或 --with-config-file-path 编译时选项指定的位置
* 如果存在 php-SAPI.ini（SAPI 是当前所用的 SAPI 名称，因此实际文件名为 php-cli.ini 或 php-apache.ini 等），则会用它替代 php.ini。SAPI 的名称可以用 php_sapi_name() 来测定。

.. Note: Apache web 服务器在启动时会把目录转到根目录，这将导致 PHP 尝试在根目录下读取 php.ini，如果存在的话。

由扩展库处理的 php.ini 指令，其文档分别在各扩展库的页面。内核配置选项见附录。不过也许不是所有的 PHP 指令都在手册中有文档说明。要得到自己的 PHP 版本中的配置指令完整列表，请阅读 php.ini 文件，其中都有注释。此外，也许从 Git 得到的» 最新版 php.ini 也有帮助。

Example #1 php.ini 例子

.. code-block:: ini

 ; any text on a line after an unquoted semicolon (;) is ignored
 [php] ; section markers (text within square brackets) are also ignored
 ; Boolean values can be set to either:
 ;    true, on, yes
 ; or false, off, no, none
 register_globals = off
 track_errors = yes

 ; you can enclose strings in double-quotes
 include_path = ".:/usr/local/lib/php"

 ; backslashes are treated the same as any other character
 include_path = ".;c:\php\lib"

自 PHP 5.1.0 起，有可能在 .ini 文件内引用已存在的 .ini 变量。例如：open_basedir = ${open_basedir} ":/new/dir"。
