.. _pseudo:

本文档中使用的伪类型
=====================

.. _mixed:

mixed
-------

mixed 说明一个参数可以接受多种不同的（但并不必须是所有的）类型。

例如 gettype() 可以接受所有的 PHP 类型， str_replace() 可以接受字符串和数组。

.. _number:

number
--------

number 说明一个参数可以是 integer 或者 float。

.. _callback:

callback
---------

有些诸如 call_user_function() 或 usort() 的函数接受用户自定义的函数作为一个参数。Callback 函数不仅可以是一个简单的函数，它还可以是一个对象的方法，包括静态类的方法。

一个 PHP 函数用函数名字符串来传递。可以传递任何内置的或者用户自定义的函数，除了语言结构如 array()， echo， empty()， eval()， exit()， isset()， list()， print 和 unset()。

一个对象的方法以数组的形式来传递，数组的下标 0 指明对象名，下标 1 指明方法名。

对于没有实例化为对象的静态类，要传递其方法，将数组 0 下标指明的对象名换成该类的名称即可。

除了普通的用户定义的函数外，也可以使用 create_function()来创建一个匿名的回调函数(callback)。

Example #1 回调函数(callback)示例

.. code-block:: php

 <?php 

 // 普通的回调函数
 function my_callback_function() {
    echo 'hello world!';
 }

 // 回调方法
 class MyClass {
    static function myCallbackMethod() {
        echo 'Hello World!';
    }
 }

 // Type 1: Simple callback
 call_user_func('my_callback_function'); 

 // Type 2: Static class method call
 call_user_func(array('MyClass', 'myCallbackMethod')); 

 // Type 3: Object method call
 $obj = new MyClass();
 call_user_func(array($obj, 'myCallbackMethod'));

 // Type 4: Static class method call (As of PHP 5.2.3)
 call_user_func('MyClass::myCallbackMethod');

 // Type 5: Relative static class method call (As of PHP 5.3.0)
 class A {
    public static function who() {
        echo "A\n";
    }
 }

 class B extends A {
    public static function who() {
        echo "B\n";
    }
 }

 call_user_func(array('B', 'parent::who')); // A
 ?>

.. Note:: 在 PHP4 中，必须使用引用来创建一个指向实际object，而不是它的一个拷贝。详情请见引用的解释。 In PHP4, it was necessary to use a reference to create a callback that points to the actual object, and not a copy of it. For more details, see References Explained.

.. void:

void
------

void 作为返回类型意味着函数的返回值是无用的。void作为参数列表意味着函数不接受任何参数。

.. ...:

...
--------

在函数原型中，$... 表示等等的意思。当一个函数可以接受任意个参数时使用此变量名。
