类型运算符
=================

instanceof 用于确定一个 PHP 变量是否属于某一类 class 的实例：

Example #1 instanceof 使用示例
<?php
class MyClass
{
}

class NotMyClass
{
}
$a = new MyClass;

var_dump($a instanceof MyClass);
var_dump($a instanceof NotMyClass);
?>
以上例程会输出：
bool(true)
bool(false)
instanceof　也可用来确定一个变量是不是继承自某一父类的子类的实例： can also be used to determine whether a variable is an instantiated object of a class that inherits from a parent class:

Example #2 instanceof 与继承类示例
<?php
class ParentClass
{
}

class MyClass extends ParentClass
{
}

$a = new MyClass;

var_dump($a instanceof MyClass);
var_dump($a instanceof ParentClass);
?>
以上例程会输出：
bool(true)
bool(true)
检查一个对象 不是 某个类的实例，可以使用 逻辑运算符 not。

Example #3 使用instanceof检查对象 不是 某一类的实例
<?php
class MyClass
{
}

$a = new MyClass;
var_dump(!($a instanceof stdClass));
?>
以上例程会输出：
bool(true)
最后，instanceof也可用于确定一个变量是不是实现了某个接口的对象的实例:

Example #4 Using instanceof for class
<?php
interface MyInterface
{
}

class MyClass implements MyInterface
{
}

$a = new MyClass;

var_dump($a instanceof MyClass);
var_dump($a instanceof MyInterface);
?>
以上例程会输出：
bool(true)
bool(true)
虽然 instanceof 通常直接与类名一起使用，但也可以使用对象或字符串变量：

Example #5 Using instanceof with other variables
<?php
interface MyInterface
{
}

class MyClass implements MyInterface
{
}

$a = new MyClass;
$b = new MyClass;
$c = 'MyClass';
$d = 'NotMyClass';

var_dump($a instanceof $b); // $b is an object of class MyClass
var_dump($a instanceof $c); // $c is a string 'MyClass'
var_dump($a instanceof $d); // $d is a string 'NotMyClass'
?>
以上例程会输出：
bool(true)
bool(true)
bool(false)
然而 instanceof 的使用还有一些陷阱必须了解。在 PHP 5.1.0之前，如果要检查的类名称不存在，instanceof 会调用 __autoload()。另外，如果该类没有被装载则会产生一个致命错误。可以通过使用动态类引用(dynamic class reference)或用一个包含类名的字符串变量来避开这种问题：

Example #6 避免 PHP 5.0 中 instanceof 引起的类名查找和致命错误问题
<?php
$d = 'NotMyClass';
var_dump($a instanceof $d); // no fatal error here
?>
以上例程会输出：
bool(false)
instanceof 运算符是 PHP 5 引进的。在此之前用 is_a()，但是 is_a() 已经过时了，最好用 instanceof。

参见 get_class() 和 is_a()。
