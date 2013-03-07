异常处理
=================================

.. toctree::
   :maxdepth: 2

   extending



PHP 5 添加了类似于其它语言的异常处理模块。在 PHP 代码中所产生的异常可被 throw 语句抛出并被 catch 语句捕获。需要进行异常处理的代码都必须放入 try 代码块内，以便捕获可能存在的异常。每一个 try 至少要有一个与之对应的 catch。使用多个 catch 可以捕获不同的类所产生的异常。当 try 代码块不再抛出异常或者找不到 catch 能匹配所抛出的异常时，PHP 代码就会在跳转到最后一个 catch 的后面继续执行。当然，PHP 允许在 catch 代码块内再次抛出（throw）异常。

当一个异常被抛出时，其后（译者注：指抛出异常时所在的代码块）的代码将不会继续执行，而 PHP 就会尝试查找第一个能与之匹配的 catch。如果一个异常没有被捕获，而且又没用使用 set_exception_handler() 作相应的处理的话，那么 PHP 将会产生一个严重的错误，并且输出 Uncaught Exception ... （未捕获异常）的提示信息。

Note:

PHP 内部函数主要使用错误报告, 只有现代面向对象的扩展才使用异常。但错误可以很容易的通过ErrorException转换为异常。

Tip
PHP标准库 (SPL) 提供了许多内建的异常类。

Example #1 抛出一个异常
<![CDATA[
<?php
function inverse($x) {
    if (!$x) {
        throw new Exception('Division by zero.');
    }
    else return 1/$x;
}

try {
    echo inverse(5) . "\n";
    echo inverse(0) . "\n";
} catch (Exception $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
}

// Continue execution
echo 'Hello World';
?>
以上例程会输出：
0.2
Caught exception: Division by zero.
Hello World
Example #2 嵌套的异常
<?php

class MyException extends Exception { }

class Test {
    public function testing() {
        try {
            try {
                throw new MyException('foo!');
            } catch (MyException $e) {
                /* rethrow it */
                throw $e;
            }
        } catch (Exception $e) {
            var_dump($e->getMessage());
        }
    }
}

$foo = new Test;
$foo->testing();

?>
以上例程会输出：
string(4) "foo!"
