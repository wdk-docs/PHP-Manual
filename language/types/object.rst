.. _object:

对象
=====================

对象初始化
----------

要创建一个新的对象 object, 使用 new 语句实例化一个类：

.. code-block:: php

 <?php
 class foo
 {
    function do_foo()
    {
        echo "Doing foo."; 
    }
 }

 $bar = new foo;
 $bar->do_foo();
 ?>

详细讨论参见手册中 类与对象 章节。

转换为对象
-----------

如果将一个对象转换成对象，它将不会有任何变化。如果其它任何类型的值被转换成对象，将会实例化一个内置类 stdClass 的对象。如果该值为 NULL，则新的实例为空。数组转换成对象将使键名成为属性名并具有相对应的值。对于任何其它的值，名为 scalar 的成员变量将包含该值。

.. code-block:: php

 <?php
 $obj = (object) 'ciao';
 echo $obj->scalar;  // outputs 'ciao'
 ?>
