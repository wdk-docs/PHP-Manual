Date/Time 函数
==============

checkdate
----------

验证一个格里高里日期

.. versionadded:: PHP4,5

.. php:method:: checkdate ( $month , $day , $year )

   .. php:attr:: 检查由参数构成的日期的合法性。如果每个参数都正确定义了则会被认为是有效的。

   :param int $month: month 的值是从 1 到 12
   :param int $day: Day 的值在给定的 month 所应该具有的天数范围之内，闰年已经考虑进去了
   :param int $year: year 的值是从 1 到 32767
   :returns: 如果给出的日期有效则返回 TRUE，否则返回 FALSE

例 #1 checkdate() 例子::

   var_dump(checkdate(12, 31, 2000));
   var_dump(checkdate(2, 29, 2001));


以上例程会输出::

   bool(true)
   bool(false)

date_default_timezone_get
-------------------------

.. versionadded:: 5.1.0

.. php:method:: date_default_timezone_get()

   .. php:attr:: — 取得一个脚本中所有日期时间函数所使用的默认时区
   
   :returns: 返回一个 string

说明
^^^^^

string date_default_timezone_get ( void )

本函数返回默认时区，使用如下“假定”的顺序:

* 用 date_default_timezone_set() 函数设定的时区（如果设定了的话）
* 仅仅在 PHP 5.4.0 之前： TZ 环境变量（如果非空）
* date.timezone 配置选项（如果设定了的话）
* 仅仅在 PHP 5.4.0 之前： 查询操作系统主机 (如果操作系统支持并允许)。 This uses an algorithm that has to guess the timezone. This is by no means going to work correctly for every situation. A warning is shown when this stage is reached. Do not rely on it to be guessed correctly, and set date.timezone to the correct timezone instead.
* 如果以上选择都不成功， date_default_timezone_get() 会则返回 UTC 的默认时区。

更新日志
^^^^^^^^^

====== ================================================
版本    说明
====== ================================================
5.4.0   不再使用 TZ 来推测时区。
5.4.0   不再根据操作系统的信息来推测时区，因为这是不可靠的。
====== ================================================

例 #1 获取默认时区:

.. code-block:: php

 <?php
   date_default_timezone_set('Europe/London');
   if (date_default_timezone_get()) {
       echo 'date_default_timezone_set: ' . date_default_timezone_get() . '<br />';
   }
   if (ini_get('date.timezone')) {
       echo 'date.timezone: ' . ini_get('date.timezone');
   }
 ?>

以上例程的输出类似于::

   date_default_timezone_set: Europe/London
   date.timezone: Europe/London

例 #2 获取一个时区的简写:

.. code-block:: php

 <?php
   date_default_timezone_set('America/Los_Angeles');
   echo date_default_timezone_get() . ' => ' . date('e') . ' => ' . date('T');
 ?>

以上例程会输出::

   America/Los_Angeles => America/Los_Angeles => PST

.. seealso::

   * date_default_timezone_set() - 设定用于一个脚本中所有日期时间函数的默认时区
   * 所支持的时区列表

