DateTime 类
==============

简介
-----

表示日期和时间。

类摘要
-------

.. php:class:: DateTime

   .. php:attr:: 时间日期类

   .. php:const:: ATOM

      格式：Y-m-d\TH:i:s(例: 2005-08-15T15:52:01+00:00)
   
   .. php:const:: COOKIE

      格式：l, d-M-y H:i:s T(例: Monday, 15-Aug-05 15:52:01 UTC)
   
   .. php:const:: ISO8601

      格式：Y-m-d\TH:i:sO(例: 2005-08-15T15:52:01+0000)
   
   .. php:const:: RFC822

      格式：D, d M y H:i:s O(例: Mon, 15 Aug 05 15:52:01 +0000)
   
   .. php:const:: RFC850

      格式：l, d-M-y H:i:s T(例: Monday, 15-Aug-05 15:52:01 UTC)
   
   .. php:const:: RFC1036

      格式：D, d M y H:i:s O(例: Mon, 15 Aug 05 15:52:01 +0000)
   
   .. php:const:: RFC1123

      格式：D, d M Y H:i:s O(例: Mon, 15 Aug 2005 15:52:01 +0000)
   
   .. php:const:: RFC2822

      格式：D, d M Y H:i:s O(Mon, 15 Aug 2005 15:52:01 +0000)
   
   .. php:const:: RFC3339

      格式：Y-m-d\TH:i:sP 同DATE_ATOM (自从 PHP 5.1.3)
   
   .. php:const:: RSS

      格式：D, d M Y H:i:s O(Mon, 15 Aug 2005 15:52:01 +0000)
   
   .. php:const:: W3C

      格式：Y-m-d\TH:i:sP World Wide Web Consortium (例: 2005-08-15T15:52:01+00:00)

   .. php:method:: construct([$time[,$timezone]])

      :param string $now: 日期时间字符串.
      :param DateTimeZone $timezone: $time的DateTimeZone对象 
      :returns: 新DateTime实例. 过程化风格在失败时返回 FALSE.
      :exception: Emits Exception in case of an error.

   .. php:method:: add([$object,]$interval)

      :param DateTime $object: 仅过程化风格：由 date_create() 返回的 DateTime 类型的对象。此函数会修改这个对象。
      :param DateInterval $interval: DateInterval 对象
      :returns: 返回被修改的 DateTime 对象， 失败返回 FALSE.

   .. php:method:: createFromFormat ( $format ,$time [, $timezone ] )

      :param string $format:
      :param string $time:
      :param DateTimeZone $timezone:
      :returns: 新DateTime实例 或者在失败时返回 FALSE.

   .. php:method:: diff ( DateTime $datetime2 [, bool $absolute = false ] )
   
      :param DateTime $datetime2:
      :param bool $absolute:
      :returns: DateInterval对象，表示两个日期之间的差异 或者在失败时返回 FALSE.
   
   .. php:method:: format ( $format )
   
      :param string $format:

   .. php:method:: getLastErrors ( void )

   .. php:method:: getOffset ( void )

   .. php:method:: getTimestamp ( void )

   .. php:method:: getTimezone ( void )

   .. php:method:: modify ( $modify )
   
      :param string $modify:

   .. php:method:: __set_state ( $array )
   
      :param array $array:

   .. php:method:: setDate ( $year , $month , $day )
   
      :param int $year:
      :param int $month:
      :param int $day:

   .. php:method:: setISODate ( $year , $week [, $day] )
      
      :param int $year:
      :param int $week:
      :param int $day: 默认1

   .. php:method:: setTime ( $hour , $minute [, $second] )

      :param int $hour:
      :param int $minute:
      :param int $second: 默认0

   .. php:method:: setTimestamp ( $unixtimestamp )

      :param int $unixtimestamp:

   .. php:method:: setTimezone ( $timezone )

      :param DateTimeZone $timezone:

   .. php:method:: sub ( $interval )

      :param DateInterval $interval:

   .. php:method:: __wakeup ( void )

更新日志
--------------

===== ==============================================================================================
版本  说明
===== ==============================================================================================
5.2.2 比较DateTime对象的比较操作符改为按预期工作。在此之前，所有的DateTime对象被认为是相等的 (使用 ==).
===== ==============================================================================================

