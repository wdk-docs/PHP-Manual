.. _null:

NULL
=====

特殊的 NULL 值表示一个变量没有值。NULL 类型唯一可能的值就是 NULL。

.. Note:: NULL 类型是 PHP 4 引进的。

在下列情况下一个变量被认为是 NULL：

* 被赋值为 NULL。
* 尚未被赋值。
* 被 unset()。

语法
---------

NULL 类型只有一个值，就是大小写不敏感的关键字 NULL（你可以写成NULL，也可以写成null）。

.. code-block:: php

 <?php
 $var = NULL;
 ?>

参见 is_null() 和 unset()。

转换到 NULL
-------------

将一个变量转换为 null 类型将会删除该变量并且unset它的值。
