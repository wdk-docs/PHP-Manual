错误控制运算符
============================

PHP 支持一个错误控制运算符：@。当将其放置在一个 PHP 表达式之前，该表达式可能产生的任何错误信息都被忽略掉。

如果激活了 track_errors 特性，表达式所产生的任何错误信息都被存放在变量 $php_errormsg 中。此变量在每次出错时都会被覆盖，所以如果想用它的话就要尽早检查。

<?php
/* Intentional file error */
$my_file = @file ('non_existent_file') or
    die ("Failed opening file: error was '$php_errormsg'");

// this works for any expression, not just functions:
$value = @$cache[$key];
// will not issue a notice if the index $key doesn't exist.

?>
Note: @ 运算符只对表达式有效。对新手来说一个简单的规则就是：如果能从某处得到值，就能在它前面加上 @ 运算符。例如，可以把它放在变量，函数和 include 调用，常量，等等之前。不能把它放在函数或类的定义之前，也不能用于条件结构例如 if 和 foreach 等。

参见 error_reporting() 及手册中错误处理及日志函数的有关章节。

Warning
目前的“@”错误控制运算符前缀甚至使导致脚本终止的严重错误的错误报告也失效。这意味着如果在某个不存在或类型错误的函数调用前用了“@”来抑制错误信息，那脚本会没有任何迹象显示原因而死在那里。
