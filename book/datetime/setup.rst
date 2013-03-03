安装/配置
============

需求
----

构建此扩展不需要其他扩展。

安装
----

使用这些函数不需要安装，它们是 PHP 核心的一部分。

.. note:: Getting the latest timezone database

 The latest version of the timezone database can be installed via PECL's » timezonedb.

.. note:: Experimental DateTime support in PHP 5.1.x

 Although the DateTime class (and related functions) are enabled by default since PHP 5.2.0, it is possible to add experimental support into PHP 5.1.x by using the following flag before configure/compile: CFLAGS=-DEXPERIMENTAL_DATE_SUPPORT=1

运行时配置
----------

这些函数的行为受 php.ini 中的设置影响。

日期／时间配置选项

=======================  ========= ============= ===================
名字                      默认      可修改范围    更新日志
=======================  ========= ============= ===================
date.default_latitude    "31.7667" PHP_INI_ALL   自 PHP 5.0.0 起可用
date.default_longitude   "35.2333" PHP_INI_ALL   自 PHP 5.0.0 起可用
date.sunrise_zenith      "90.83"   PHP_INI_ALL   自 PHP 5.0.0 起可用
date.sunset_zenith       "90.83"   PHP_INI_ALL   自 PHP 5.0.0 起可用
date.timezone            ""        PHP_INI_ALL   自 PHP 5.0.0 起可用
=======================  ========= ============= ===================

有关 PHP_INI_* 样式的更多详情与定义，见 Where a configuration setting may be set。

这是配置指令的简短说明。

* date.default_latitude :ref:`float <float>` 默认纬度。
* date.default_longitude :ref:`float <float>` 默认经度。
* date.sunrise_zenith :ref:`float <float>` 默认日出天顶。
* date.sunset_zenith :ref:`float <float>` 默认日落天顶。
* date.timezone :ref:`string <string>` 在未设定 TZ 环境变量时用于所有日期／时间函数的默认时区。优先顺序在 date_default_timezone_get() 页面中有说明。 支持的时区可参见 所支持的时区列表。

.. note:: 前四个配置选项目前仅用于 date_sunrise() 和 date_sunset()。

资源类型
-----------

此扩展没有定义资源类型。


