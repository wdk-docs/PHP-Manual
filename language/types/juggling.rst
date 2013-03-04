.. _juggling:

类型转换的判别
===============

PHP 在变量定义中不需要（或不支持）明确的类型定义；变量类型是根据使用该变量的上下文所决定的。也就是说，如果把一个字符串值赋给变量 var，var 就成了一个字符串。如果又把一个整型值赋给 var，那它就成了一个整数。

PHP 的自动类型转换的一个例子是加号“+”。如果任何一个操作数是浮点数，则所有的操作数都被当成浮点数，结果也是浮点数。否则操作数会被解释为整数，结果也是整数。注意这并没有改变这些操作数本身的类型；改变的仅是这些操作数如何被求值以及表达式本身的类型。

.. code-block:: php

 <?php
 $foo = "0";  // $foo 是字符串 (ASCII 48)
 $foo += 2;   // $foo 现在是一个整数 (2)
 $foo = $foo + 1.3;  // $foo 现在是一个浮点数 (3.3)
 $foo = 5 + "10 Little Piggies"; // $foo 是整数 (15)
 $foo = 5 + "10 Small Pigs";     // $foo 是整数 (15)
 ?>

如果上面两个例子看上去古怪的话，参见字符串转换为数值。

如果要强制将一个变量当作某种类型来求值，参见类型强制转换一节。如果要改变一个变量的类型，参见 settype()。

如果想要测试本节中任何例子的话，可以用 var_dump() 函数。

.. Note:: 自动转换为 数组 的行为目前没有定义。

Also, because PHP supports indexing into strings via offsets using the same syntax as array indexing, the following example holds true for all PHP versions:

.. code-block:: php

 <?php
 $a    = 'car'; // $a is a string
 $a[0] = 'b';   // $a is still a string
 echo $a;       // bar
 ?>

请参阅访问和修改字符串中的字符一节以获取更多信息。

类型强制转换
-------------

PHP 中的类型强制转换和 C 中的非常像：在要转换的变量之前加上用括号括起来的目标类型。

.. code-block:: php

 <?php
 $foo = 10;   // $foo is an integer
 $bar = (boolean) $foo;   // $bar is a boolean
 ?>

允许的强制转换有：

* (int), (integer) - 转换为 整型(integer)
* (bool), (boolean) - 转换为 布尔型(boolean)
* (float), (double), (real) - 转换为 浮点型(float)
* (string) - 转换为 字符串(string)
* (binary) - 转换为二进制 字符串(string) (PHP 6)
* (array) - 转换为 数组(array)
* (object) - 转换为 对象(object)
* (unset) - 转换为 NULL (PHP 5)
* (binary) 转换会在结果前面加上前缀'b'，PHP 5.2.1 新增。

注意在括号内允许有空格和制表符，所以下面两个例子功能相同：

.. code-block:: php

 <?php
 $foo = (int) $bar;
 $foo = ( int ) $bar;
 ?>

将 字符串(string)文字和变量转换为二进制 字符串(string)：

.. code-block:: php

 <?php
 $binary = (binary)$string;
 $binary = b"binary string";
 ?>

.. Note: 可以将变量放置在双引号中的方式来代替将变量转换成 字符串(string)s：

.. code-block:: php

 <?php
 $foo = 10;            // $foo 是一个整数
 $str = "$foo";        // $str 是一个字符串
 $fst = (string) $foo; // $fst 也是一个字符串

 // 输出 "they are the same"
 if ($fst === $str) {
    echo "they are the same";
 }
 ?>

有时在类型之间强制转换时确切地会发生什么可能不是很明显。更多信息见如下小节：

* 转换为布尔型
* 转换为整型
* 转换为浮点型
* 转换为字符串
* 转换为数组
* 转换为对象
* 转换为资源
* 转换为 NULL
* 类型比较表
