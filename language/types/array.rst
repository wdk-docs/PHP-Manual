.. _array:

数组
=====================


PHP 中的 数组 实际上是一个有序映射。映射是一种把 values 关联到 keys 的类型。此类型在很多方面做了优化，因此可以把它当成真正的数组，或列表（向量），散列表（是映射的一种实现），字典，集合，栈，队列以及更多可能性。数组元素的值也可以是另一个数组。树形结构和多维数组也是允许的。

解释这些结构超出了本手册的范围，但对于每种结构至少会提供一个例子。要得到这些结构的更多信息，建议参考有关此广阔主题的其它著作。

语法
-----

定义数组 array()
^^^^^^^^^^^^^^^^^^

可以用 array() 语言结构来新建一个 array。它接受任意数量用逗号分隔的 键(key) => 值(value) 对::

 array(  key =>  value
      , ...
      )
 // 键(key) 可是是一个 整数(integer) 或 字符串(string)
 // 值(value) 可以是任意类型的值
 
.. code-block:: php
 
 <?php
 $arr = array("foo" => "bar", 12 => true);

 echo $arr["foo"]; // bar
 echo $arr[12];    // 1
 ?>

以上例程在PHP 5.3中的输出::

 string(1) "b"
 bool(true)
 string(1) "b"
 bool(true)
 string(1) "a"
 bool(true)
 string(1) "b"
 bool(true)

以上例程在PHP 5.4中的输出::

 string(1) "b"
 bool(true)

 Warning: Illegal string offset '1.0' in /tmp/t.php on line 7
 string(1) "b"
 bool(false)

 Warning: Illegal string offset 'x' in /tmp/t.php on line 9
 string(1) "a"
 bool(false)
 string(1) "b"
 bool(false)

key 可以是 integer 或者 string。如果key是一个 integer 的标准表示，则被解释为整数（例如 "8" 将被解释为 8，而 "08" 将被解释为 "08"）。key 中的浮点数被取整为 integer。在 PHP 中索引数组与关联 数组 是相同的，它们都可以同时包含 整型 和 字符串 的下标。

值可以是任意的 PHP 类型。

.. code-block:: php

 <?php
 $arr = array("somearray" => array(6 => 5, 13 => 9, "a" => 42));

 echo $arr["somearray"][6];    // 5
 echo $arr["somearray"][13];   // 9
 echo $arr["somearray"]["a"];  // 42
 ?>

如果对给出的值没有指定键名，则取当前最大的整数索引值，而新的键名将是该值加一。如果指定的键名已经有了值，则该值会被覆盖。

.. code-block:: php

 <?php
 // 这个数组与下面的数组相同 ...
 array(5 => 43, 32, 56, "b" => 12);

 // ...
 array(5 => 43, 6 => 32, 7 => 56, "b" => 12);
 ?>

.. Warning:: 自 PHP 4.3.0 起，上述的索引生成方法改变了。如今如果给一个当前最大键名是负值的数组添加一个新值，则新生成的的索引将为零（0）。以前新生成的索引为当前最大索引加一，和正值的索引相同。

使用 TRUE 作为键名将使 integer 1 成为键名。使用 FALSE 作为键名将使 integer 0 成为键名。使用 NULL 作为键名将等同于使用空字符串。使用空字符串作为键名将新建（或覆盖）一个用空字符串作为键名的值，这和用空的方括号不一样。

不能用数组和对象作为键(key)。这样做会导致一个警告：Illegal offset type。

用方括号的语法新建／修改
^^^^^^^^^^^^^^^^^^^^^^^^^

可以通过明示地设定值来改变一个现有的数组。

这是通过在方括号内指定键名来给数组赋值实现的。也可以省略键名，在这种情况下给变量名加上一对空的方括号（“[]”）::

 $arr[key] = value;
 $arr[] = value;
 // key 可以是 integer 或 string
 // value 可以是任意类型的值

如果 $arr 还不存在，将会新建一个。这也是一种定义数组的替换方法。要改变一个值，只要给它赋一个新值。如果要删除一个键名／值对，要对它用 unset()。

.. code-block:: php

 <?php
 $arr = array(5 => 1, 12 => 2);

 $arr[] = 56;    // This is the same as $arr[13] = 56;
                 // at this point of the script

 $arr["x"] = 42; // This adds a new element to
                 // the array with key "x"
                 
 unset($arr[5]); // This removes the element from the array

 unset($arr);    // This deletes the whole array
 ?>

.. Note: 如上所述，如果给出方括号但没有指定键名，则取当前最大整数索引值，新的键名将是该值 + 1。如果当前还没有整数索引，则键名将为 0。如果指定的键名已经有值了，该值将被覆盖。

注意这里所使用的最大整数键名不一定当前就在数组中。它只要在上次数组重新生成索引后曾经存在过就行了。以下面的例子来说明：

.. code-block:: php

 <?php
 // 创建一个简单的数组
 $array = array(1, 2, 3, 4, 5);
 print_r($array);

 // 现在删除其中的所有元素，但保持数组本身不变:
 foreach ($array as $i => $value) {
     unset($array[$i]);
 }
 print_r($array);

 // 添加一个单元（注意新的键名是 5，而不是你可能以为的 0）
 $array[] = 6;
 print_r($array);

 // 重新索引：
 $array = array_values($array);
 $array[] = 7;
 print_r($array);
 ?>

以上例程会输出::

 Array
 (
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
    [4] => 5
 )
 Array
 (
 )
 Array
 (
    [5] => 6
 )
 Array
 (
    [0] => 6
    [1] => 7
 )

实用函数
--------------

有很多操作数组的函数，参见数组函数一节。

.. Note: unset() 函数允许删除数组中的某个键。但要注意数组将不会重建索引。 If a true "remove and shift" behavior is desired, the array can be reindexed using the array_values() function.

.. code-block:: php

 <?php
 $a = array(1 => 'one', 2 => 'two', 3 => 'three');
 unset($a[2]);
 /* will produce an array that would have been defined as
    $a = array(1 => 'one', 3 => 'three');
    and NOT
    $a = array(1 => 'one', 2 =>'three');
 */

 $b = array_values($a);
 // Now $b is array(0 => 'one', 1 =>'three')
 ?>

foreach 控制结构是专门用于数组的。它提供了一个简单的方法来遍历数组。

数组做什么和不做什么
------------------------

为什么 $foo[bar] 错了？
^^^^^^^^^^^^^^^^^^^^^^^^^^

应该始终在用字符串表示的数组索引上加上引号。例如用 $foo['bar'] 而不是 $foo[bar]。但是为什么 $foo[bar] 错了呢？可能在老的脚本中见过如下语法：

.. code-block:: php

 <?php
 $foo[bar] = 'enemy';
 echo $foo[bar];
 // etc
 ?>

这样是错的，但可以正常运行。那么为什么错了呢？原因是此代码中有一个未定义的常量（bar）而不是字符串（'bar'－注意引号），而 PHP 可能会在以后定义此常量，不幸的是你的代码中有同样的名字。它能运行，是因为 PHP 自动将裸字符串（没有引号的字符串且不对应于任何已知符号）转换成一个其值为该裸字符串的正常字符串。例如，如果没有常量定义为 bar，PHP 将把它替代为 'bar' 并使用之。

.. Note:: 这并不意味着总是给键名加上引号。用不着给键名为常量或变量的加上引号，否则会使 PHP 不能解析它们。

.. code-block:: php

 <?php
 error_reporting(E_ALL);
 ini_set('display_errors', true);
 ini_set('html_errors', false);
 // Simple array:
 $array = array(1, 2);
 $count = count($array);
 for ($i = 0; $i < $count; $i++) {
    echo "\nChecking $i: \n";
    echo "Bad: " . $array['$i'] . "\n";
    echo "Good: " . $array[$i] . "\n";
    echo "Bad: {$array['$i']}\n";
    echo "Good: {$array[$i]}\n";
 }
 ?>

以上例程会输出::

 Checking 0: 
 Notice: Undefined index:  $i in /path/to/script.html on line 9
 Bad: 
 Good: 1
 Notice: Undefined index:  $i in /path/to/script.html on line 11
 Bad: 
 Good: 1

 Checking 1: 
 Notice: Undefined index:  $i in /path/to/script.html on line 9
 Bad: 
 Good: 2
 Notice: Undefined index:  $i in /path/to/script.html on line 11
 Bad: 
 Good: 2

演示此行为的更多例子：

.. code-block:: php

 <?php
 // Show all errors
 error_reporting(E_ALL);

 $arr = array('fruit' => 'apple', 'veggie' => 'carrot');

 // Correct
 print $arr['fruit'];  // apple
 print $arr['veggie']; // carrot

 // Incorrect.  This works but also throws a PHP error of level E_NOTICE because
 // of an undefined constant named fruit
 // 
 // Notice: Use of undefined constant fruit - assumed 'fruit' in...
 print $arr[fruit];    // apple

 // This defines a constant to demonstrate what's going on.  The value 'veggie'
 // is assigned to a constant named fruit.
 define('fruit', 'veggie');

 // Notice the difference now
 print $arr['fruit'];  // apple
 print $arr[fruit];    // carrot

 // The following is okay, as it's inside a string. Constants are not looked for
 // within strings, so no E_NOTICE occurs here
 print "Hello $arr[fruit]";      // Hello apple

 // With one exception: braces surrounding arrays within strings allows constants
 // to be interpreted
 print "Hello {$arr[fruit]}";    // Hello carrot
 print "Hello {$arr['fruit']}";  // Hello apple

 // This will not work, and will result in a parse error, such as:
 // Parse error: parse error, expecting T_STRING' or T_VARIABLE' or T_NUM_STRING'
 // This of course applies to using superglobals in strings as well
 print "Hello $arr['fruit']";
 print "Hello $_GET['foo']";

 // Concatenation is another option
 print "Hello " . $arr['fruit']; // Hello apple
 ?>

当打开 error_reporting 来显示 E_NOTICE 级别的错误（例如将其设为 E_ALL）时将看到这些错误。默认情况下 error_reporting 被关闭不显示这些。

和在语法一节中规定的一样，在方括号（“[”和“]”）之间必须有一个表达式。这意味着可以这样写：

.. code-block:: php

 <?php
 echo $arr[somefunc($bar)];
 ?>

这是一个用函数返回值作为数组索引的例子。PHP 也可以用已知常量，可能之前已经见过

.. code-block:: php

 <?php
 $error_descriptions[E_ERROR]   = "A fatal error has occured";
 $error_descriptions[E_WARNING] = "PHP issued a warning";
 $error_descriptions[E_NOTICE]  = "This is just an informal notice";
 ?>

注意 E_ERROR 也是个合法的标识符，就和第一个例子中的 bar 一样。但是上一个例子实际上和如下写法是一样的：

.. code-block:: php

 <?php
 $error_descriptions[1] = "A fatal error has occured";
 $error_descriptions[2] = "PHP issued a warning";
 $error_descriptions[8] = "This is just an informal notice";
 ?>

因为 E_ERROR 等于 1, 等等.

那么为什么这样做不好？
^^^^^^^^^^^^^^^^^^^^^^^

也许有一天，PHP 开发小组可能会想新增一个常量或者关键字，或者用户可能希望以后在自己的程序中引入新的常量，那就有麻烦了。例如已经不能这样用 empty 和 default 这两个词了，因为他们是保留字。

.. Note:: 重申一次，在双引号字符串中，不给索引加上引号是合法的因此 "$foo[bar]"是合法的（“合法”的原文为valid。在实际测试中，这么做确实可以访问数组的该元素，但是会报一个常量未定义的notice。无论如何，强烈建议不要使用$foo[bar]这样的写法，而要使用$foo['bar']来访问数组中元素。--haohappy注）。至于为什么参见以上的例子和字符串中的变量解析中的解释。

转换为数组
------------

对于任意类型: integer, float, string, boolean and resource,如果将一个值转换为数组，将得到一个仅有一个元素的数组（其下标为 0），该元素即为此标量的值。换句话说， (array)$scalarValue 与 array($scalarValue) 完全一样。

If an object is converted to an array, the result is an array whose elements are the object's properties. The keys are the member variable names, with a few notable exceptions: integer properties are unaccessible; private variables have the class name prepended to the variable name; protected variables have a '*' prepended to the variable name. These prepended values have null bytes on either side. This can result in some unexpected behaviour:

.. code-block:: php

 <?php

 class A {
    private $A; // This will become '\0A\0A'
 }

 class B extends A {
    private $A; // This will become '\0B\0A'
    public $AA; // This will become 'AA'
 }

 var_dump((array) new B());
 ?>

The above will appear to have two keys named 'AA', although one of them is actually named '\0A\0A'.

将 NULL 转换到 数组(array) 会得到一个空的数组。

比较
----------

可能使用 array_diff() 和数组运算符来比较数组。

例子
--------

PHP 中的数组类型有非常多的用途，因此这里有一些例子展示数组的完整威力。

.. code-block:: php

 <?php
 // This:
 $a = array( 'color' => 'red',
            'taste' => 'sweet',
            'shape' => 'round',
            'name'  => 'apple',
            4        // key will be 0
          );

 $b = array('a', 'b', 'c');

 // . . .is completely equivalent with this:
 $a = array();
 $a['color'] = 'red';
 $a['taste'] = 'sweet';
 $a['shape'] = 'round';
 $a['name']  = 'apple';
 $a[]        = 4;        // key will be 0

 $b = array();
 $b[] = 'a';
 $b[] = 'b';
 $b[] = 'c';

 // After the above code is executed, $a will be the array
 // array('color' => 'red', 'taste' => 'sweet', 'shape' => 'round', 
 // 'name' => 'apple', 0 => 4), and $b will be the array 
 // array(0 => 'a', 1 => 'b', 2 => 'c'), or simply array('a', 'b', 'c').
 ?>

例 #1 Using array()

.. code-block:: php

 <?php
 // Array as (property-)map
 $map = array( 'version'    => 4,
              'OS'         => 'Linux',
              'lang'       => 'english',
              'short_tags' => true
            );
            
 // strictly numerical keys
 $array = array( 7,
                8,
                0,
                156,
                -10
              );
 // this is the same as array(0 => 7, 1 => 8, ...)

 $switching = array(         10, // key = 0
                    5    =>  6,
                    3    =>  7, 
                    'a'  =>  4,
                            11, // key = 6 (maximum of integer-indices was 5)
                    '8'  =>  2, // key = 8 (integer!)
                    '02' => 77, // key = '02'
                    0    => 12  // the value 10 will be overwritten by 12
                  );
                  
 // empty array
 $empty = array();         
 ?>

例 #2 集合

.. code-block:: php

 <?php
 $colors = array('red', 'blue', 'green', 'yellow');

 foreach ($colors as $color) {
     echo "Do you like $color?\n";
 }
 ?>

以上例程会输出::

 Do you like red?
 Do you like blue?
 Do you like green?
 Do you like yellow?

直接改变数组的值在 PHP 5 中可以通过引用传递来做到。之前的版本需要需要采取变通的方法：

例 #3 集合

.. code-block:: php

 <?php
 // PHP 5
 foreach ($colors as &$color) {
     $color = strtoupper($color);
 }
 unset($color); /* ensure that following writes to
 $color will not modify the last array element */

 // Workaround for older versions
 foreach ($colors as $key => $color) {
    $colors[$key] = strtoupper($color);
 }

 print_r($colors);
 ?>

以上例程会输出::

 Array
 (
    [0] => RED
    [1] => BLUE
    [2] => GREEN
    [3] => YELLOW
 )

本例生成一个下标从1开始的数组。This example creates a one-based array.

例 #4 下标从1开始的数组

.. code-block:: php

 <?php
 $firstquarter  = array(1 => 'January', 'February', 'March');
 print_r($firstquarter);
 ?>

以上例程会输出::

 Array 
 (
    [1] => 'January'
    [2] => 'February'
    [3] => 'March'
 )

例 #5 填充数组

.. code-block:: php

 <?php
 // fill an array with all items from a directory
 $handle = opendir('.');
 while (false !== ($file = readdir($handle))) {
     $files[] = $file;
 }
 closedir($handle); 
 ?>

数组是有序的。也可以使用不同的排序函数来改变顺序。更多信息参见数组函数。可以用 count() 函数来数出数组中元素的个数。

例 #6 数组排序

.. code-block:: php

 <?php
 sort($files);
 print_r($files);
 ?>

因为数组中的值可以为任意值，也可是另一个数组。这样可以产生递归或多维数组。

例 #7 递归和多维数组

.. code-block:: php

 <?php
 $fruits = array ( "fruits"  => array ( "a" => "orange",
                                       "b" => "banana",
                                       "c" => "apple"
                                     ),
                  "numbers" => array ( 1,
                                       2,
                                       3,
                                       4,
                                       5,
                                       6
                                     ),
                  "holes"   => array (      "first",
                                       5 => "second",
                                            "third"
                                     )
                );

 // Some examples to address values in the array above 
 echo $fruits["holes"][5];    // prints "second"
 echo $fruits["fruits"]["a"]; // prints "orange"
 unset($fruits["holes"][0]);  // remove "first"

 // Create a new multi-dimensional array
 $juices["apple"]["green"] = "good"; 
 ?>

数组(Array) 的赋值总是会涉及到值的拷贝。使用 引用操作符 通过引用来拷贝数组。

.. code-block:: php

 <?php
 $arr1 = array(2, 3);
 $arr2 = $arr1;
 $arr2[] = 4; // $arr2 is changed,
              // $arr1 is still array(2, 3)

 $arr3 = &$arr1;
 $arr3[] = 4; // now $arr1 and $arr3 are the same
 ?>
