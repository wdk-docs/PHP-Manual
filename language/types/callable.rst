.. callback:

Callbacks
===========

Callbacks can be denoted by callable type hint as of PHP 5.4. This documentation used callback type information for the same purpose.

Some functions like call_user_func() or usort() accept user-defined callback functions as a parameter. Callback functions can not only be simple functions, but also object methods, including static class methods.

Passing
---------

A PHP function is passed by its name as a string. Any built-in or user-defined function can be used, except language constructs such as: array(), echo, empty(), eval(), exit(), isset(), list(), print or unset().

A method of an instantiated object is passed as an array containing an object at index 0 and the method name at index 1.

Static class methods can also be passed without instantiating an object of that class by passing the class name instead of an object at index 0. As of PHP 5.2.3, it is also possible to pass 'ClassName::methodName'.

Apart from common user-defined function, create_function() can also be used to create an anonymous callback function. As of PHP 5.3.0 it is possible to also pass a closure to a callback parameter.

Example #1 Callback function examples

.. code-block:: php

 <?php 

 // An example callback function
 function my_callback_function() {
    echo 'hello world!';
 }

 // An example callback method
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

Example #2 Callback example using a Closure

.. code-block:: php

 <?php
 // Our closure
 $double = function($a) {
     return $a * 2;
 };

 // This is our range of numbers
 $numbers = range(1, 5);

 // Use the closure as a callback here to 
 // double the size of each element in our 
 // range
 $new_numbers = array_map($double, $numbers);

 print implode(' ', $new_numbers);
 ?>

以上例程会输出::

 2 4 6 8 10

.. Note:: In PHP 4, it was necessary to use a reference to create a callback that points to the actual object, and not a copy of it. For more details, see References Explained.

.. Note:: 在函数中注册有多个回调内容时(如使用 call_user_func() 与 call_user_func_array())，如在前一个回调中有未捕获的异常，其后的将不再被调用。
