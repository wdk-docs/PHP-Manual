运行时配置
============


运行时配置

FPM 配置文件为 ``php-fpm.conf``，其语法类似 ``php.ini`` 。

全局配置
--------

.. confval:: pid

 :ref:`string` PID文件的位置. 默认为空.

.. confval:: error_log

 :ref:`string` 错误日志的位置. 默认： 安装路径#INSTALL_PREFIX#/log/php-fpm.log.

.. confval:: log_level

 :ref:`string` 错误级别. 可用级别为: alert（必须立即处理）, error（错误情况）, warning（警告情况）, notice（一般重要信息）, debug（调试信息）. 默认: notice.

.. confval:: emergency_restart_threshold

 :ref:`int` 如果子进程在emergency_restart_interval设定的时间内收到该参数设定次数的SIGSEGV 或者 SIGBUS退出信息号，则FPM会重新启动。 0 表示 '关闭该功能'. 默认值: 0 (关闭).

.. confval:: emergency_restart_interval
 
 :ref:`mixed` emergency_restart_interval用于设定平滑重启的间隔时间. 这么做有助于解决加速器中共享内存的使用问题. 可用单位: s(秒), m(分), h(小时), 或者 d(天). 默认单位： s(秒). 默认值: 0 (关闭).

.. confval:: process_control_timeout

 :ref:`mixed` 设置子进程接受主进程复用信号的超时时间. 可用单位: s(秒), m(分), h(小时), 或者 d(天) 默认单位: s(秒). 默认值: 0.

.. confval:: daemonize

 :ref:`boolean` 设置FPM在后台运行. 设置 'no' 将 FPM 保持在前台运行用于调试. 默认值: yes.

运行配置
--------

在FPM中，可以使用不同的设置来运行多个进程池。 这些设置可以针对每个进程池单独设置。

.. confval:: listen

 :ref:`string` 设置接受FastCGI请求的地址. 可用格式为: 'ip:port', 'port', '/path/to/unix/socket'. 每个进程池都需要设置.

.. confval:: listen.backlog

 :ref:`int` 设置 listen(2) 的半连接队列长度. '-1' 表示无限制. 默认值: -1.

.. confval:: listen.allowed_clients

 :ref:`string` 设置允许连接到FastCGI的服务器IPV4地址. 等同于PHP FastCGI (5.2.2+)中的 FCGI_WEB_SERVER_ADDRS环境变量. 仅对TCP监听起作用. 每个地址是用逗号分隔. 如果没有设置或者为空，则允许任何服务器请求连接. 默认值: any.

.. confval:: listen.owner

 :ref:`string` 如果使用，表示设置Unix套接字的权限. 在Linux中，读写权限必须设置，以便用于WEB服务器连接. 在很多BSD派生的系统中可以忽略权限允许自由连接. 默认值: 运行所使用的用户合租, 权限为0666.

.. confval:: listen.group

 :ref:`string` 参见 listen.owner.

.. confval:: listen.mode

 :ref:`string` 参见 listen.owner.

.. confval:: user

 :ref:`string` FPM 进程运行的Unix用户. 必须设置.

.. confval:: group

 :ref:`string` FPM 进程运行的Unix用户组. 如果没有设置，则默认用户的组被使用.

.. confval:: pm

 :ref:`string` 设置进程管理器如何管理子进程. 可用值: static, dynamic. 必须设置.

 **static** - 子进程的数量是固定的 (pm.max_children).

 **dynamic** - 子进程的数量在下面配置的基础上动态设置: pm.max_children, pm.start_servers, pm.min_spare_servers, pm.max_spare_servers.

.. confval:: pm.max_children

 :ref:`int` 子进程的数量，pm 设置为 static 时表示创建的， pm 设置为 dynamic 时表示最大可创建的. 必须设置.

 该选项设置可以同时提供服务的请求数限制. 类似 Apache 的 mpm_prefork 中 MaxClients 的设置和 普通PHP FastCGI中的 PHP_FCGI_CHILDREN 环境变量.

.. confval:: pm.start_servers

 :ref:`int` 设置启动时创建的子进程数目. 仅在 pm 设置为 dynamic 时使用. 默认值: min_spare_servers + (max_spare_servers - min_spare_servers) / 2.

.. confval:: pm.min_spare_servers

 :ref:`int` 设置空闲服务进程的最低数目. 仅在 pm 设置为 dynamic 时使用. 必须设置.

.. confval:: pm.max_spare_servers

 :ref:`int` 设置空闲服务进程的最大数目. 仅在 pm 设置为 dynamic 时使用. 必须设置.

.. confval:: pm.max_requests

 :ref:`int` 设置每个子进程重生之前服务的请求数. 对于可能存在内存泄漏的第三方模块来说是非常有用的. 如果设置为 '0' 则一直接受请求. 等同于 PHP_FCGI_MAX_REQUESTS 环境变量. 默认值: 0.

.. confval:: pm.status_path

 :ref:`string` FPM状态页面的网址. 如果没有设置, 则无法访问状态页面. 默认值: none.

.. confval:: ping.path

 :ref:`string` FPM监控页面的ping网址. 如果没有设置, 则无法访问ping页面. 该页面用于外部检测FPM是否存活并且可以响应请求. 请注意必须以斜线开头 (/).

.. confval:: ping.response

 :ref:`string` 用于定义ping请求的返回相应. 返回为 HTTP 200 的 text/plain 格式文本. 默认值: pong.

.. confval:: request_terminate_timeout

 设置单个请求的超时中止时间. 该选项可能会对php.ini设置中的'max_execution_time'因为某些特殊原因没有中止运行的脚本有用. 设置为 '0' 表示 'Off'. Available units: s(econds)(default), m(inutes), h(ours), or d(ays). Default value: 0.

.. confval:: request_slowlog_timeout

 :ref:`mixed` 当一个请求该设置的超时时间后，就会将对应的PHP调用堆栈信息完整写入到慢日志中. 设置为 '0' 表示 'Off'. 可用单位: s(秒)(默认), m(分), h(小时), 或者 d(天). 默认值: 0.

.. confval:: slowlog

 :ref:`string` 慢请求的记录日志. 默认值: #INSTALL_PREFIX#/log/php-fpm.log.slow.

.. confval:: rlimit_files

 :ref:`int` 设置文件打开描述符的rlimit限制. 默认值: 系统定义值.

.. confval:: rlimit_core

 :ref:`int` 设置核心rlimit最大限制值. 可用值: 'unlimited' 、0或者正整数. 默认值: 系统定义值.

.. confval:: chroot

 :ref:`string` 启动时的Chroot目录. 所定义的目录需要是绝对路径. 如果没有设置, 则chroot不被使用.

.. confval:: chdir

 :ref:`string` 设置启动目录，启动时会自动Chdir到该目录. 所定义的目录需要是绝对路径. 默认值: 当前目录，或者/目录（chroot时）.

.. confval:: catch_workers_output

 :ref:`bool` 重定向运行过程中的stdout和stderr到主要的错误日志文件中. 如果没有设置, stdout 和 stderr 将会根据FastCGI的规则被重定向到 /dev/null . 默认值: 空.

你还可以在为一个运行池传递附加的环境变量，或者更新PHP的配置值. 你可以在 php-fpm.conf 中下如下面的配置参数来做到：

例 #1 给运行池传递环境变量和设置PHP的配置值

.. code-block:: ini

       env[HOSTNAME] = $HOSTNAME
       env[PATH] = /usr/local/bin:/usr/bin:/bin
       env[TMP] = /tmp
       env[TMPDIR] = /tmp
       env[TEMP] = /tmp

       php_admin_value[sendmail_path] = /usr/sbin/sendmail -t -i -f www@my.domain.com
       php_flag[display_errors] = off
       php_admin_value[error_log] = /var/log/fpm-php.www.log
       php_admin_flag[log_errors] = on
       php_admin_value[memory_limit] = 32M

PHP配置值通过 php_value 或者 php_flag 设置，并且会覆盖以前的值. 请注意 disable_functions 或者 disable_classes 在 php.ini 之中定义的值不会被覆盖掉, 但是会将新的设置附加在原有值的后面.
使用 php_admin_value 或者 php_admin_flag 定义的值，不能被PHP代码中的 ini_set() 覆盖.


