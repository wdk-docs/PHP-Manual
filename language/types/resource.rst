.. _resource:

资源类型
=====================

资源是一种特殊变量，保存了到外部资源的一个引用。资源是通过专门的函数来建立和使用的。所有这些函数及其相应资源类型见附录。

.. Note:: 资源类型是 PHP 4 引进的。

参见 get_resource_type()。

转换为资源
-----------

由于资源类型变量保存有为打开文件、数据库连接、图形画布区域等的特殊句柄，因此将其它类型的值转换为资源没有意义。

释放资源
----------

由于 PHP4 Zend 引擎引进了引用计数系统，可以自动检测到一个资源不再被引用了（和 Java 一样）。这种情况下此资源使用的所有外部资源都会被垃圾回收系统释放。因此，很少需要手工释放内存。 Thanks to the reference-counting system introduced with PHP 4's Zend Engine, a resource with no more references to it is detected automatically, and it is freed by the garbage collector. For this reason, it is rarely necessary to free the memory manually.

.. Note:: 持久数据库连接比较特殊，它们不会被垃圾回收系统销毁。参见数据库永久连接一章。
