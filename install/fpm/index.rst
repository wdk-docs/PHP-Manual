FPM
====
.. toctree::
   :maxdepth: 1
   
   install
   configuration
   
FPM (FastCGI 进程管理器) 用于替换PHP FastCGI的大部分附加功能，对于高负载网站是非常有用的。

它的功能包括：

* 支持平滑停止/启动的高级进程管理功能；
* 可以工作于不同的uid/gid/chroot环境下，并监听不同的端口和使用不同的php.ini配置文件（可取代safe_mode的设置）；
* stdout 和 stderr 日志记录;
* 在发生意外情况的时候能够重新启动并缓存被破坏的opcode;
* 文件上传优化支持;
* "慢日志" - 记录脚本 (不仅记录文件名，还记录PHP backtrace信息，可以使用ptrace或者类似工具读取和分析远程进程的运行数据) 运行所导致的异常缓慢;
* fastcgi_finish_request() - 特殊功能：用于在请求完成和刷新数据后，继续在后台执行耗时的工作 (录入视频转换、统计处理等)；
* 动态/静态子进程产生;
* 基本SAPI运行状态信息 (类似Apache的 mod_status);
* 基于php.ini的配置文件.

.. todo:: 研究ptrace

