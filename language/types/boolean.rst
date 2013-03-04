.. _bool:

布尔类型
========

这是最简单的类型。boolean 表达了真值，可以为 ``TRUE`` 或 ``FALSE`` 。

.. note:: 布尔类型是 PHP 4 引进的。

语法

要指定一个布尔值，使用关键字 ``TRUE`` 或 ``FALSE``。两个都不区分大小写。

.. code-block:: php

 <?php
 $foo = True; // assign the value TRUE to $foo
 ?>

通常你用某些运算符返回 boolean 值，并将其传递给控制流程。

.. code-block:: php

 <?php
 // == 是一个操作符，它检测两个变量是否相等，并返回一个布尔值
 if ($action == "show_version") {
    echo "The version is 1.23";
 }
 // 这样做是不必要的...
 if ($show_separators == TRUE) {
    echo "<hr>\n";
 }
 // ...因为可以使用下面这种简单的方式：
 if ($show_separators) {
     echo "<hr>\n";
 }
 ?>

转换为布尔值

要明确地将一个值转换成 boolean，用 (bool) 或者 (boolean) 来强制转换。但是很多情况下不需要用强制转换，因为当运算符，函数或者流程控制结构需要一个 boolean 参数时，该值会被自动转换。

参见类型戏法。

当转换为 boolean 时，以下值被认为是 FALSE：

the 布尔值 FALSE 自身
the 整型值 0 (零)
the 浮点型值 0.0 (零)
空 字符串, 以及 字符串 "0"
不包括任何元素的数组
不包括任何成员变量的对象（仅PHP 4.0 适用）
特殊类型 NULL (包括尚未设定的变量)
从没有任何标记（tags）的XML文档生成的SimpleXML 对象
所有其它值都被认为是 TRUE（包括任何资源）。

.. warning:: -1 和其它非零值（不论正负）一样，被认为是 TRUE！

.. code-block:: php

 <?php
 var_dump((bool) "");        // bool(false)
 var_dump((bool) 1);         // bool(true)
 var_dump((bool) -2);        // bool(true)
 var_dump((bool) "foo");     // bool(true)
 var_dump((bool) 2.3e5);     // bool(true)
 var_dump((bool) array(12)); // bool(true)
 var_dump((bool) array());   // bool(false)
 var_dump((bool) "false");   // bool(true)
 ?>
