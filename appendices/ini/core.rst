核心配置选项说明
=================

该列表只包含核心的 php.ini 配置选项。扩展的配置选项在各个扩展的文档页面分别被描述。有关 session 的选项可以在 sessions 页面找到。

Httpd 选项
---------------

Httpd 选项
名字	默认	可修改范围	更新日志
async_send	"0"	PHP_INI_ALL

语言选项
-------------

语言和杂类配置选项
名字	默认	可修改范围	更新日志
short_open_tag	"1"	PHP_INI_ALL	在 PHP 4.0.0 时是 PHP_INI_ALL。 在 PHP < 5.3.0 时是 PHP_INI_PERDIR。
asp_tags	"0"	PHP_INI_PERDIR	在 PHP 4.0.0 时是 PHP_INI_ALL。
precision	"14"	PHP_INI_ALL	 
serialize_precision	"17"	PHP_INI_ALL	从 PHP 4.3.2 起可用。在 PHP 5.3.5以前，默认值为 100
y2k_compliance	"1"	PHP_INI_ALL	在 PHP 5.4.0 中移除该选项。
allow_call_time_pass_reference	"1"	PHP_INI_PERDIR	在 PHP 4.0.0 时是 PHP_INI_ALL。 在 PHP 5.4.0 中移除该选项。
disable_functions	""	php.ini only	从 PHP 4.0.1 起可用。
disable_classes	""	php.ini only	从 PHP 4.3.2 起可用。
exit_on_timeout	""	PHP_INI_ALL	从 PHP 5.3.0 起可用。
expose_php	"1"	php.ini only	 
zend.multibyte	"0"	PHP_INI_ALL	从 PHP 5.4.0 起可用
zend.script_encoding	NULL	PHP_INI_ALL	从 PHP 5.4.0 起可用
zend.signal_check	"0"	PHP_INI_SYSTEM	从 PHP 5.4.0 起可用
zend.ze1_compatibility_mode	"0"	PHP_INI_ALL	从 PHP 5.0.0起可用。 在 PHP 5.3.0 中移除该选项
detect_unicode	"1"	PHP_INI_ALL	从 PHP 5.1.0起可用。 此已废弃的 特性即将 被移除。
这是配置指令的简短说明。

short_open_tag boolean
决定是否允许使用 PHP 代码开始标志的缩写形式（<? ?>）。如果要和 XML 结合使用 PHP，可以禁用此选项以便于嵌入使用 <?xml ?>。否则还可以通过 PHP 来输出，例如：<?php echo '<?xml version="1.0"'; ?>。如果禁用了，必须使用 PHP 代码开始标志的完整形式（<?php ?>）。

Note:

本指令也会影响到缩写形式 <?=，它和 <? echo 等价。使用此缩写需要 short_open_tag 的值为 On。 从 PHP 5.4.0 起， <?= 总是可用的。

asp_tags boolean
除了通常的 <?php ?> 标志之外还允许使用 ASP 风格的标志 <% %>。这也包括了输出变量值的缩写 <%= $value %>。更多信息见从 HTML 中分离一节。
precision integer
浮点数中显示有效数字的位数。
serialize_precision integer
The number of significant digits stored while serializing floating point numbers.
y2k_compliance boolean
强制 2000 年兼容（在不兼容的浏览器中会出问题）。
allow_call_time_pass_reference boolean
在函数调用时参数被按照引用传递时是否发出警告。此方法已不被赞成并在 PHP/Zend 未来的版本中很可能不再支持。鼓励使用的方法是在函数定义中指定哪些参数应该用引用传递。鼓励大家尝试关闭此选项并确保脚本能够正常运行，以确保该脚本也能在未来的版本中运行（每次使用此特性都会收到一条警告）。

在函数调用时通过引用传递参数是不推荐的，因为它影响到了代码的整洁。如果函数的参数没有声明作为引用传递，函数可以通过未写入文档的方法修改其参数。要避免其副作用，最好仅在函数声明时指定那个参数需要通过引用传递。

参见引用的解释。

Changelog for allow_call_time_pass_reference
版本	说明
5.4.0	 从 PHP 中移除。
5.3.0	 Emits an E_DEPRECATED level error.
5.0.0	 Deprecated, and generates an E_COMPILE_WARNING level error.
expose_php boolean
决定是否暴露 PHP 被安装在服务器上（例如在 Web 服务器的信息头中加上其签名：X-Powered-By: PHP/5.3.7)。 The PHP logo guids are also exposed, thus appending them to the URL of a PHP enabled site will display the appropriate logo (e.g., » http://www.php.net/?=PHPE9568F34-D428-11d2-A769-00AA001ACF42). This also affects the output of phpinfo(), as when disabled, the PHP logo and credits information will not be displayed.

See also php_logo_guid() and phpcredits().

disable_functions string
本指令允许你基于安全原因禁止某些函数。接受逗号分隔的函数名列表作为参数。 disable_functions 不受安全模式的影响。 本指令只能设置在 php.ini 中。例如不能将其设置在 httpd.conf。
disable_classes string
本指令可以使你出于安全的理由禁用某些类。用逗号分隔类名。disable_classes 不受安全模式的影响。 本指令只能设置在 php.ini 中。例如不能将其设置在 httpd.conf。
Note: 可用性说明
本指令自 PHP 4.3.2 起可用。

zend.ze1_compatibility_mode boolean
Enable compatibility mode with Zend Engine 1 (PHP 4). It affects the cloning, casting (objects with no properties cast to FALSE or 0), and comparing of objects. In this mode, objects are passed by value instead of reference by default.

See also the section titled Migrating from PHP 4 to PHP 5.

Warning
This feature has been DEPRECATED and REMOVED as of PHP 5.3.0.

zend.multibyte boolean
Enables parsing of source files in multibyte encodings.

zend.script_encoding string
This value will be used unless a declare(encoding=...) directive appears at the top of the script.

zend.signal_check boolean
To check for replaced signal handlers on shutdown.

detect_unicode boolean
Check for BOM (Byte Order Mark) and see if the file contains valid multibyte characters. This detection is performed before processing of __halt_compiler(). Available only in Zend Multibyte mode.

exit_on_timeout boolean
This is an Apache1 mod_php-only directive that forces an Apache child to exit if a PHP execution timeout occurred. Such a timeout causes an internal longjmp() call in Apache1 which can leave some extensions in an inconsistent state. By terminating the process any outstanding locks or memory will be cleaned up.

Resource Limits
------------------

Resource Limits
名字	默认	可修改范围	更新日志
memory_limit	"128M"	PHP_INI_ALL	"8M" before PHP 5.2.0, "16M" in PHP 5.2.0
这是配置指令的简短说明。

memory_limit integer
This sets the maximum amount of memory in bytes that a script is allowed to allocate. This helps prevent poorly written scripts for eating up all available memory on a server. Note that to have no memory limit, set this directive to -1.

Prior to PHP 5.2.1, in order to use this directive it had to be enabled at compile time by using --enable-memory-limit in the configure line. This compile-time flag was also required to define the functions memory_get_usage() and memory_get_peak_usage() prior to 5.2.1.

当使用 integer 时, 其值以字节来衡量。还可以使用在FAQ中描述的速记符。
See also: max_execution_time.

Performance Tuning
--------------------

Performance Tuning
名字	默认	可修改范围	更新日志
realpath_cache_size	"16K"	PHP_INI_SYSTEM	从 PHP 5.1.0 起可用。
realpath_cache_ttl	"120"	PHP_INI_SYSTEM	从 PHP 5.1.0 起可用。
这是配置指令的简短说明。

realpath_cache_size integer
Determines the size of the realpath cache to be used by PHP. This value should be increased on systems where PHP opens many files, to reflect the quantity of the file operations performed.

realpath_cache_ttl integer
Duration of time (in seconds) for which to cache realpath information for a given file or directory. For systems with rarely changing files, consider increasing the value.

Data Handling
-------------------

Data Handling Configuration Options
名字	默认	可修改范围	更新日志
track_vars	"On"	PHP_INI_??	 
arg_separator.output	"&"	PHP_INI_ALL	从 PHP 4.0.5 起可用。
arg_separator.input	"&"	PHP_INI_PERDIR	从 PHP 4.0.5 起可用。
variables_order	"EGPCS"	PHP_INI_PERDIR	在 PHP <= 5.0.5 时是 PHP_INI_ALL。
request_order	""	PHP_INI_PERDIR	从 PHP 5.3.0 起可用
auto_globals_jit	"1"	PHP_INI_PERDIR	从 PHP 5.0.0 起可用。
register_globals	"0"	PHP_INI_PERDIR	在 PHP <= 4.2.3 时是 PHP_INI_ALL。 在 PHP 5.4.0 中移除该选项。
register_argc_argv	"1"	PHP_INI_PERDIR	在 PHP <= 4.2.3 时是 PHP_INI_ALL。
register_long_arrays	"1"	PHP_INI_PERDIR	从 PHP 5.0.0. Deprecated in PHP 5.3.0. Removed in PHP 5.4.0 起可用。
post_max_size	"8M"	PHP_INI_PERDIR	在 PHP <= 4.2.3 时是 PHP_INI_SYSTEM。 从 PHP 4.0.3 起可用。
gpc_order	"GPC"	PHP_INI_ALL	 
auto_prepend_file	NULL	PHP_INI_PERDIR	在 PHP <= 4.2.3 时是 PHP_INI_ALL。
auto_append_file	NULL	PHP_INI_PERDIR	在 PHP <= 4.2.3 时是 PHP_INI_ALL。
default_mimetype	"text/html"	PHP_INI_ALL	 
default_charset	""	PHP_INI_ALL	 
always_populate_raw_post_data	"0"	PHP_INI_PERDIR	在 PHP <= 4.2.3 时是 PHP_INI_ALL。 从 PHP 4.1.0 起可用。
allow_webdav_methods	"0"	PHP_INI_PERDIR	 
这是配置指令的简短说明。

track_vars boolean
If enabled, then Environment, GET, POST, Cookie, and Server variables can be found in the global associative arrays $_ENV, $_GET, $_POST, $_COOKIE, and $_SERVER.

Note that as of PHP 4.0.3, track_vars is always turned on.

arg_separator.output string
The separator used in PHP generated URLs to separate arguments.

arg_separator.input string
List of separator(s) used by PHP to parse input URLs into variables.

Note:

Every character in this directive is considered as separator!

variables_order string
Sets the order of the EGPCS (Environment, Get, Post, Cookie, and Server) variable parsing. For example, if variables_order is set to "SP" then PHP will create the superglobals $_SERVER and $_POST, but not create $_ENV, $_GET, and $_COOKIE. Setting to "" means no superglobals will be set.

If the deprecated register_globals directive is on, then variables_order also configures the order the ENV, GET, POST, COOKIE and SERVER variables are populated in global scope. So for example if variables_order is set to "EGPCS", register_globals is enabled, and both $_GET['action'] and $_POST['action'] are set, then $action will contain the value of $_POST['action'] as P comes after G in our example directive value.

Warning
In both the CGI and FastCGI SAPIs, $_SERVER is also populated by values from the environment; S is always equivalent to ES regardless of the placement of E elsewhere in this directive.

Note:

The content and order of $_REQUEST is also affected by this directive.

request_order string
This directive describes the order in which PHP registers GET, POST and Cookie variables into the _REQUEST array. Registration is done from left to right, newer values override older values.

If this directive is not set, variables_order is used for $_REQUEST contents.

Note that the default distribution php.ini files does not contain the 'C' for cookies, due to security concerns.

auto_globals_jit boolean
When enabled, the SERVER and ENV variables are created when they're first used (Just In Time) instead of when the script starts. If these variables are not used within a script, having this directive on will result in a performance gain.

The PHP directives register_globals, register_long_arrays, and register_argc_argv must be disabled for this directive to have any affect. Since PHP 5.1.3 it is not necessary to have register_argc_argv disabled.

Warning
Usage of SERVER and ENV variables is checked during the compile time so using them through e.g. variable variables will not cause their initialization.

register_globals boolean
Whether or not to register the EGPCS (Environment, GET, POST, Cookie, Server) variables as global variables.

As of » PHP 4.2.0, this directive defaults to off.

Please read the security chapter on Using register_globals for related information.

Please note that register_globals cannot be set at runtime ( ini_set()). Although, you can use .htaccess if your host allows it as described above. An example .htaccess entry: php_flag register_globals off.

Note:

register_globals is affected by the variables_order directive.

Warning
This feature has been DEPRECATED as of PHP 5.3.0 and REMOVED as of PHP 5.4.0.

register_argc_argv boolean
Tells PHP whether to declare the argv & argc variables (that would contain the GET information). See also command line.
register_long_arrays boolean
Tells PHP whether or not to register the deprecated long $HTTP_*_VARS type predefined variables. When On (default), long predefined PHP variables like $HTTP_GET_VARS will be defined. If you're not using them, it's recommended to turn them off, for performance reasons. Instead, use the superglobal arrays, like $_GET. This directive became available in PHP 5.0.0.
Warning
This feature has been DEPRECATED as of PHP 5.3.0 and REMOVED as of PHP 5.4.0.

enable_post_data_reading boolean
Disabling this option causes $_POST and $_FILES not to be populated. The only way to read postdata will then be through the php://input stream wrapper. This can be useful to proxy requests or to process the POST data in a memory efficient fashion.
post_max_size integer
Sets max size of post data allowed. This setting also affects file upload. To upload large files, this value must be larger than upload_max_filesize. If memory limit is enabled by your configure script, memory_limit also affects file uploading. Generally speaking, memory_limit should be larger than post_max_size. 当使用 integer 时, 其值以字节来衡量。还可以使用在FAQ中描述的速记符。 If the size of post data is greater than post_max_size, the $_POST and $_FILES superglobals are empty. This can be tracked in various ways, e.g. by passing the $_GET variable to the script processing the data, i.e. <form action="edit.php?processed=1">, and then checking if $_GET['processed'] is set.
Note:

PHP allows shortcuts for bit values, including K (kilo), M (mega) and G (giga). PHP will do the conversions automatically if you use any of these. Be careful not to exceed the 32 bit signed integer limit (if you're using 32bit versions) as it will cause your script to fail.

gpc_order string
Set the order of GET/POST/COOKIE variable parsing. The default setting of this directive is "GPC". Setting this to "GP", for example, will cause PHP to completely ignore cookies and to overwrite any GET method variables with POST-method variables of the same name.

Note:

This option is not available in PHP 4. Use variables_order instead.

auto_prepend_file string
Specifies the name of a file that is automatically parsed before the main file. The file is included as if it was called with the require function, so include_path is used.

The special value none disables auto-prepending.

auto_append_file string
Specifies the name of a file that is automatically parsed after the main file. The file is included as if it was called with the require function, so include_path is used.

The special value none disables auto-appending.

Note: If the script is terminated with exit(), auto-append will not occur.

default_mimetype string
default_charset string
PHP always outputs a character encoding by default in the Content-type: header. To disable sending of the charset, simply set it to be empty.

always_populate_raw_post_data boolean
Always populate the $HTTP_RAW_POST_DATA containing the raw POST data. Otherwise, the variable is populated only with unrecognized MIME type of the data. However, the preferred method for accessing the raw POST data is php://input. $HTTP_RAW_POST_DATA is not available with enctype="multipart/form-data".

allow_webdav_methods boolean
Allow handling of WebDAV http requests within PHP scripts (eg. PROPFIND, PROPPATCH, MOVE, COPY, etc.). This directive does not exist as of PHP 4.3.2. If you want to get the post data of those requests, you have to set always_populate_raw_post_data as well.

See also: magic_quotes_gpc, magic_quotes_runtime, and magic_quotes_sybase.

Paths and Directories
------------------------

Paths and Directories Configuration Options
名字	默认	可修改范围	更新日志
include_path	".;/path/to/php/pear"	PHP_INI_ALL	 
open_basedir	NULL	PHP_INI_ALL	PHP_INI_SYSTEM in PHP < 5.3.0
doc_root	NULL	PHP_INI_SYSTEM	 
user_dir	NULL	PHP_INI_SYSTEM	 
extension_dir	"/path/to/php"	PHP_INI_SYSTEM	 
extension	NULL	php.ini only	 
zend_extension	NULL	php.ini only	 
zend_extension_debug	NULL	php.ini only	 
zend_extension_debug_ts	NULL	php.ini only	 
zend_extension_ts	NULL	php.ini only	 
cgi.check_shebang_line	"1"	PHP_INI_SYSTEM	从 PHP 5.2.0 起可用。
cgi.fix_pathinfo	"1"	PHP_INI_SYSTEM	从 PHP 4.3.0. PHP_INI_ALL prior to PHP 5.2.1 起可用。
cgi.force_redirect	"1"	PHP_INI_SYSTEM	从 PHP 4.2.0. PHP_INI_ALL prior to PHP 5.2.1 起可用。
cgi.redirect_status_env	NULL	PHP_INI_SYSTEM	从 PHP 4.2.0. PHP_INI_ALL prior to PHP 5.2.1 起可用。
cgi.rfc2616_headers	"0"	PHP_INI_ALL	从 PHP 4.3.0 起可用。
fastcgi.impersonate	"0"	PHP_INI_SYSTEM	从 PHP 4.3.0. PHP_INI_ALL prior to PHP 5.2.1 起可用。
fastcgi.logging	"1"	PHP_INI_SYSTEM	从 PHP 4.3.0. PHP_INI_ALL prior to PHP 5.2.1 起可用。
这是配置指令的简短说明。

include_path string
Specifies a list of directories where the require, include, fopen(), file(), readfile() and file_get_contents() functions look for files. The format is like the system's PATH environment variable: a list of directories separated with a colon in Unix or semicolon in Windows.

PHP considers each entry in the include path separately when looking for files to include. It will check the first path, and if it doesn't find it, check the next path, until it either locates the included file or returns with a warning or an error. You may modify or set your include path at runtime using set_include_path().

Example #1 Unix include_path
include_path=".:/php/includes"
Example #2 Windows include_path
include_path=".;c:\php\includes"
Using a . in the include path allows for relative includes as it means the current directory. However, it is more efficient to explicitly use include './file' than having PHP always check the current directory for every include.

open_basedir string
将 PHP 所能打开的文件限制在指定的目录树，包括文件本身。本指令不受安全模式打开或者关闭的影响。

当一个脚本试图用例如 fopen() 或者 gzopen() 打开一个文件时，该文件的位置将被检查。当文件在指定的目录树之外时 PHP 将拒绝打开它。所有的符号连接都会被解析，所以不可能通过符号连接来避开此限制。

特殊值 . 指明脚本的工作目录将被作为基准目录。但这有些危险，因为脚本的工作目录可以轻易被 chdir() 而改变。

在 httpd.conf 文件中中，open_basedir 可以像其它任何配置选项一样用“php_admin_value open_basedir none”的方法关闭（例如某些虚拟主机中）。

在 Windows 中，用分号分隔目录。在任何其它系统中用冒号分隔目录。作为 Apache 模块时，父目录中的 open_basedir 路径自动被继承。

用 open_basedir 指定的限制实际上是前缀，不是目录名。也就是说“open_basedir = /dir/incl”也会允许访问“/dir/include”和“/dir/incls”，如果它们存在的话。如果要将访问限制在仅为指定的目录，用斜线结束路径名。例如：“open_basedir = /dir/incl/”。

Note:

支持多个目录是 3.0.7 加入的。

默认是允许打开所有文件。

doc_root string
PHP's "root directory" on the server. Only used if non-empty. If PHP is configured with 安全模式, no files outside this directory are served. If PHP was not compiled with FORCE_REDIRECT, you should set doc_root if you are running PHP as a CGI under any web server (other than IIS). The alternative is to use the cgi.force_redirect configuration below.

user_dir string
The base name of the directory used on a user's home directory for PHP files, for example public_html .

extension_dir string
In what directory PHP should look for dynamically loadable extensions. See also: enable_dl, and dl().

extension string
Which dynamically loadable extensions to load when PHP starts up.

zend_extension string
Absolute path to dynamically loadable Zend extension (for example APD) to load when PHP starts up.

zend_extension_debug string
Variant of zend_extension for extensions compiled with debug info.

zend_extension_debug_ts string
Variant of zend_extension for extensions compiled with debug info and thread safety.

zend_extension_ts string
Variant of zend_extension for extensions compiled with thread safety.

cgi.check_shebang_line boolean
Controls whether CGI PHP checks for line starting with #! (shebang) at the top of the running script. This line might be needed if the script support running both as stand-alone script and via PHP CGI. PHP in CGI mode skips this line and ignores its content if this directive is turned on.

cgi.fix_pathinfo boolean
Provides real PATH_INFO/ PATH_TRANSLATED support for CGI. PHP's previous behaviour was to set PATH_TRANSLATED to SCRIPT_FILENAME, and to not grok what PATH_INFO is. For more information on PATH_INFO, see the CGI specs. Setting this to 1 will cause PHP CGI to fix its paths to conform to the spec. A setting of zero causes PHP to behave as before. It is turned on by default. You should fix your scripts to use SCRIPT_FILENAME rather than PATH_TRANSLATED.

cgi.force_redirect boolean
cgi.force_redirect is necessary to provide security running PHP as a CGI under most web servers. Left undefined, PHP turns this on by default. You can turn it off at your own risk.

Note:

Windows Users: When using IIS this option must be turned off. For OmniHTTPD or Xitami the same applies.

cgi.redirect_status_env string
If cgi.force_redirect is turned on, and you are not running under Apache or Netscape (iPlanet) web servers, you may need to set an environment variable name that PHP will look for to know it is OK to continue execution.

Note:

Setting this variable may cause security issues, know what you are doing first.

cgi.rfc2616_headers int
Tells PHP what type of headers to use when sending HTTP response code. If it's set 0, PHP sends a Status: header that is supported by Apache and other web servers. When this option is set to 1, PHP will send » RFC 2616 compliant headers. Leave it set to 0 unless you know what you're doing.

fastcgi.impersonate string
FastCGI under IIS (on WINNT based OS) supports the ability to impersonate security tokens of the calling client. This allows IIS to define the security context that the request runs under. mod_fastcgi under Apache does not currently support this feature (03/17/2002) Set to 1 if running under IIS. Default is zero.

fastcgi.logging boolean
Turns on SAPI logging when using FastCGI. Default is to enable logging.

File Uploads
---------------

File Uploads Configuration Options
名字	默认	可修改范围	更新日志
file_uploads	"1"	PHP_INI_SYSTEM	在 PHP <= 4.2.3 时是 PHP_INI_ALL。 从 PHP 4.0.3 起可用。
upload_tmp_dir	NULL	PHP_INI_SYSTEM	 
max_input_nesting_level	64	PHP_INI_PERDIR	从 PHP 5.3.9 起可用。
max_input_vars	1000	PHP_INI_PERDIR	从 PHP 5.3.9 起可用。
upload_max_filesize	"2M"	PHP_INI_PERDIR	在 PHP <= 4.2.3 时是 PHP_INI_ALL。
max_file_uploads	20	PHP_INI_SYSTEM	从 PHP 5.2.12 起可用。
这是配置指令的简短说明。

file_uploads boolean or integer
Whether or not to allow HTTP file uploads. See also the upload_max_filesize, upload_tmp_dir, and post_max_size directives.

当使用 integer 时, 其值以字节来衡量。还可以使用在FAQ中描述的速记符。
upload_tmp_dir string
The temporary directory used for storing files when doing file upload. Must be writable by whatever user PHP is running as. If not specified PHP will use the system's default.

If the directory specified here is not writable, PHP falls back to the system default temporary directory. If open_basedir is on, then the system default directory must be allowed for an upload to succeed.

upload_max_filesize integer
The maximum size of an uploaded file.

当使用 integer 时, 其值以字节来衡量。还可以使用在FAQ中描述的速记符。
max_file_uploads integer
The maximum number of files allowed to be uploaded simultaneously. Starting with PHP 5.3.4, upload fields left blank on submission do not count towards this limit.

General SQL
---------------

General SQL Configuration Options
名字	默认	可修改范围	更新日志
sql.safe_mode	"0"	PHP_INI_SYSTEM	 
这是配置指令的简短说明。

sql.safe_mode boolean
If turned on, database connect functions that specify default values will use those values in place of supplied arguments. For default values see connect function documentation for the relevant database.

Windows Specific
------------------

Windows Specific Configuration Options
名字	默认	可修改范围	更新日志
windows_show_crt_warning	"0"	PHP_INI_ALL	从 PHP 5.4.0 起可用。
这是配置指令的简短说明。

windows_show_crt_warning boolean
This directive shows the Windows CRT warnings when enabled. These warnings were displayed by default until PHP 5.4.0.
