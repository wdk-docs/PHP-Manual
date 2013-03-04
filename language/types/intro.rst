简介
=====

PHP 支持8种基本的数据类型。

四种标量类型：

* boolean （布尔型）
* integer （整型）
* float （浮点型, 也称作 double)
* string （字符串）

两种复合类型：

* array （数组）
* object （对象）

最后是三种特殊类型：

* resource
* NULL
* callable

为了确保代码的易读性，本手册还介绍了一些伪类型：

* mixed
* number
* callback
* $....

可能还会读到一些关于“双精度（double）”类型的参考。实际上 double 和 float 是相同的，由于一些历史的原因，这两个名称同时存在。

变量的类型通常不是由程序员设定的，确切地说，是由 PHP 根据该变量使用的上下文在运行时决定的。

.. Note:: 如果想查看某个表达式的值和类型，用 var_dump()。

如果只是想得到一个易读懂的类型的表达方式用于调试，用 gettype()。要查看某个类型，不要用 gettype()，而用 is_type 函数。以下是一些范例：

.. code-block:: php

 <?php
 $a_bool = TRUE;   // a boolean
 $a_str  = "foo";  // a string
 $a_str2 = 'foo';  // a string
 $an_int = 12;     // an integer

 echo gettype($a_bool); // prints out:  boolean
 echo gettype($a_str);  // prints out:  string

 // If this is an integer, increment it by four
 if (is_int($an_int)) {
     $an_int += 4;
 }

 // If $bool is a string, print it out
 // (does not print out anything)
 if (is_string($a_bool)) {
     echo "String: $a_bool";
 }
 ?>

如果要将一个变量强制转换为某类型，可以对其使用强制转换或者 settype() 函数。

注意变量根据其当时的类型在特定场合下会表现出不同的值。更多信息见类型戏法。此外，你还可以参考 PHP 类型比较表看不同类型相互比较的例子。
