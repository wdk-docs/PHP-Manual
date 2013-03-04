.. _string:

字符串
======

一个字符串 就是由一系列的字符组成，因此，一个字符就是一个字节。这就是说，一个字节只能有256种不同的变化，这也暗示了PHP无 法原生支持Unicode 。 更多信息可参考函数 utf8_encode()和 utf8_decode()。

.. note:: 一个很长的字符串是没有问题的，PHP对于字符串; 而对字符串长度的限制只和运行PHP程序的该台计 算机的内存大小有关。

语法
----

一个字符串 通过下面的4种方法来定义：

* 单引号
* 双引号
* heredoc 语法结构
* nowdoc 语法结构 (自PHP 5.3.0以后)

单引号
------

定义一个字符串 的最简单的方法是用单引号把它包围起来 (标点符号 ')。

如果想要输出一个单引号，需在它的前面加个反斜线 (\)。在单引号前或在字符串的结尾处 想要输出反斜线，输入两条 (\\)。注意，如果在任何其它的字符前加了反斜线，反斜线将会被直接输出。

.. note:: 不像双引号 和heredoc语法结构， 在单引号字符串中的变量 和特殊含义的字符将 不会 被替换。

.. code-block:: php

 <?php
   echo 'this is a simple string';

   // 可以录入多行
   echo 'You can also have embedded newlines in
      strings this way as it is
      okay to do';

   // 输出： Arnold once said: "I'll be back"
   echo 'Arnold once said: "I\'ll be back"';

   // 输出： You deleted C:\*.*?
   echo 'You deleted C:\\*.*?';

   // 输出： You deleted C:\*.*?
   echo 'You deleted C:\*.*?';

   // 输出： This will not expand: \n a newline
   echo 'This will not expand: \n a newline';

   // 输出： Variables do not $expand $either
   echo 'Variables do not $expand $either';
 ?>

双引号
------

如果字符串是包围在双引号(")中， PHP将对一些特殊的字符进行解析：

Escaped characters

===================  ==============================================
序列                  含义
===================  ==============================================
\n                    换行 (LF or 0x0A (10) in ASCII)
\r                    回车 (CR or 0x0D (13) in ASCII)
\t                    水平方向的 tab(HT or 0x09 (9) in ASCII)
\v                    竖直方向的 tab (VT or 0x0B (11) in ASCII) (since PHP 5.2.5)
\f                    换页 (FF or 0x0C (12) in ASCII) (since PHP 5.2.5)
\\                    反斜线
\$                    美金dollar标记
\"                    双引号
\[0-7]{1,3}           符合该表达式顺序的字符串是一个八进制的字符
\x[0-9A-Fa-f]{1,2}    符合该表达式顺序的字符串是一个十六进制的字符
===================  ==============================================

和单引号 字符串一样， 如果输出上述之外的字符，反斜线会被打印出来。 PHP5.1.1以 前，\\{$var} 中的反斜线还不会被显示出来。

用双引号定义的字符串最重要的特征是变量会被解析，更多信息见字符串解析。

Heredoc结构
-----------

第三种定义字符串的方法是用heredoc句法结构：<<<。在该提示 符后面，要定义个标识符，然后是一个新行。接下来是字符串 本身，最后要用前面定义的标识符作为结束标志。

结束时所引用的标识符必须在一行的开始位置， 而且，标识符的命名也要像其它标签一样遵守PHP的规则：只能包含 字母、数字和下划线，并且必须以字母和下划线作为开头。

.. warning:: 要注意的是结束标识符这行除了 可能有一个分号(;)外，绝对不能包括 其它字符。这意味着标识符不能缩进，分号的前后也不能有任何空白或tabs。更重要的是结束标识符的前面必须是个被本地 操作系统认可的新行标签，比如在UNIX和Mac OS X系统中是\n ，而结束标识符（可能有个分号）的后面也必须跟个 新行标签。

如果不遵守该规则导致结束标签不“干净”，PHP将认为它不是结束标识符而继续寻找。如果在文件结束前也没有找到一个正确的结束标识符，PHP将会在最后一 行产生一个句法错误。

Heredocs结构不能用来初始化class，而从PHP 5.3以后，则该限制只能用在包含变量的情况下。

例 #1 非法的示例

.. code-block:: php

 <?php
 class foo {
     public $bar = <<<EOT
 bar
 EOT;
 }
 ?>
 
Heredoc结构就象是没有使用双引号的双引号字符串， 这就是说在heredoc结构中引号不用被替换，但是上文中列出的字符 (\n等)也可使用。 变量将被替换，但在heredoc结构中字符串表达复杂变量时，要格外小 心。

例 #2 Heredoc结构的字符串示例

.. code-block:: php

 <?php
 $str = <<<EOD
 例 of string
 spanning multiple lines
 using heredoc syntax.
 EOD;

 /* 含有变量的更复杂示例 */
 class foo
 {
     var $foo;
     var $bar;

     function foo()
     {
         $this->foo = 'Foo';
         $this->bar = array('Bar1', 'Bar2', 'Bar3');
     }
 }

 $foo = new foo();
 $name = 'MyName';

 echo <<<EOT
 My name is "$name". I am printing some $foo->foo.
 Now, I am printing some {$foo->bar[1]}.
 This should print a capital 'A': \x41
 EOT;
 ?>

以上例程会输出::

 My name is "MyName". I am printing some Foo.
 Now, I am printing some Bar2.
 This should print a capital 'A': A

也可以把Heredoc结构用在函数参数中来传输数据：

例 #3 Heredoc结构在参数中的示例

.. code-block:: php

 <?php
 var_dump(array(<<<EOD
 foobar!
 EOD
 ));
 ?>

在PHP 5.3.0以后，也可以用Heredoc结构来初始化静态变量和类的属性和常量：

例 #4 使用Heredoc结构来初始化静态值

.. code-block:: php

 <?php
 // 静态变量
 function foo()
 {
     static $bar = <<<LABEL
 Nothing in here...
 LABEL;
 }

 // 类的常量、属性
 class foo
 {
     const BAR = <<<FOOBAR
 Constant 例
 FOOBAR;

     public $baz = <<<FOOBAR
 Property 例
 FOOBAR;
 }
 ?>

在PHP 5.3.0中还在Heredoc结构中用双引号来声明标志符：

例 #5 在heredoc结构中使用双引号

.. code-block:: php

 <?php
 echo <<<"FOOBAR"
 Hello World!
 FOOBAR;
 ?>

.. note: PHP4才引入了Heredoc结构。

Nowdoc结构
----------

就象heredoc结构类似于双引号字符串，Nowdoc结构是类似于单引号字符串的。Nowdoc结构很象heredoc结构，但是 nowdoc不进行解析操作 。 这种结构很适合用在不需要进行转义的PHP代码和其它大段文本。与SGML的 <![CDATA[ ]]> 结构是用来声明大段的不用解析的文本类似，nowdoc结构也有相同的特征。

一个nowdoc结构也用和heredocs结构一样的标记 <<<， 但是跟在后面的标志符要用 单引号括起来，就像<<<'EOT'这样。heredocs结构的所有规则也同样适用于nowdoc结 构，尤其是结束标志符的规则。

例 #6 Nowdoc结构字符串示例

.. code-block:: php

 <?php
 $str = <<<'EOD'
 例 of string
 spanning multiple lines
 using nowdoc syntax.
 EOD;

 /* 含有变量的更复杂的示例 */
 class foo
 {
     public $foo;
     public $bar;

     function foo()
     {
         $this->foo = 'Foo';
         $this->bar = array('Bar1', 'Bar2', 'Bar3');
     }
 }

 $foo = new foo();
 $name = 'MyName';

 echo <<<'EOT'
 My name is "$name". I am printing some $foo->foo.
 Now, I am printing some {$foo->bar[1]}.
 This should not print a capital 'A': \x41
 EOT;
 ?>
 
以上例程会输出::

 My name is "$name". I am printing some $foo->foo.
 Now, I am printing some {$foo->bar[1]}.
 This should not print a capital 'A': \x41

.. note: 不象 heredocs结构，nowdocs结构可以用在任意的静态数据环境中，最典型的示例是用来初始化类的属性或常量：

例 #7 表态数据的示例

.. code-block:: php

 <?php
 class foo {
     public $bar = <<<'EOT'
 bar
 EOT;
 }
 ?>
 
.. note: Nowdoc结构是在PHP 5.3.0中加入的。

变量解析
--------

当字符串用双引号或heredoc结构定义时，其中的变 量将会被解析。

这里共有两种语法规则：一种简单 规则，一种复杂规 则。简单的句法规则是最常用和最方便的， 它可以用最少的代码在一个字符串中加入变量， 数组 值，或 对象属性。

复杂的句法规则是在PHP4以后加入的，被花括号包围的表达式是其明显标记。

简单句法规则
^^^^^^^^^^^^

当PHP解析器遇到一个美元符号 ($) ， 它会和其它很多解析器一样，去尽量形成一个合法的变量名。可以用花括 号来明确变量名的界线。

.. code-block:: php

 <?php
 $beer = 'Heineken';
 echo "$beer's taste is great"; //有效；单引号"'"是非法的变量名组成元素
 echo "He drank some $beers"; //无效;字母s是有效的变量名组成元素，但是这里的变量是$beer
 echo "He drank some ${beer}s"; // 有效
 echo "He drank some {$beer}s"; // 有效
 ?>

类似的，一个 数组 索引或一个 对象 属性也可被解析。数组索引要用方括号 (]) 来表示边际， 对象属性则是和上述的变量规则相同。

.. code-block:: php

 <?php
 // 下面的例子是在字符串中引用数组
 // 当数组处于字符串外部时，要把数组的值用括号括起来且不要用花括号{ }

 // 显示所有错误
 error_reporting(E_ALL);

 $fruits = array('strawberry' => 'red', 'banana' => 'yellow');

 // 有效；但是注意在字符串外面不能这样引用数组
 echo "A banana is $fruits[banana].";

 // 有效
 echo "A banana is {$fruits['banana']}.";

 // 有效，但是PHP会先寻找常量banana
 echo "A banana is {$fruits[banana]}.";

 // 无效，要用花括号，这里将会产生一个解析错误
 echo "A banana is $fruits['banana'].";

 // 有效
 echo "A banana is " . $fruits['banana'] . ".";

 // 有效
 echo "This square is $square->width meters broad.";

 // 无效，解决方法见复杂结构
 echo "This square is $square->width00 centimeters broad.";
 ?>

如果想要表达更复杂的结构，请用复杂句法规则。

复杂句法规则
^^^^^^^^^^^^

复杂句法规则不是结构复杂而命名，而是因为它可以使用复杂的表达式。

任何想用在字符串中标量变量，数组变量或对象属性都可使用这种方法。 只需简单地像在字符串以外的地方那样写出表达式， 然后用花括号{和 }把它括起来。 由于 { 无法被转义，只有 $ 要紧挨着 {才会被认出来，可以用 {\$ 来表达 {$。下面的示例可以更好的解释：

.. code-block:: php

 <?php
 // 显示所有错误
 error_reporting(E_ALL);

 $great = 'fantastic';

 // 无效，输出: This is { fantastic}
 echo "This is { $great}";

 // 有效，输出： This is fantastic
 echo "This is {$great}";
 echo "This is ${great}";

 // 有效
 echo "This square is {$square->width}00 centimeters broad."; 

 // 有效
 echo "This works: {$arr[4][3]}";

 // 这是错误的表达式，因为就象$foo[bar] 的格式不能在字符串以外的地方使用一样。
 // 换句话说，只有在PHP能找到常量foo 的前提下才会正常工作；这里会产生一个E_NOTICE (undefined constant)级别的错误。
 echo "This is wrong: {$arr[foo][3]}"; 

 // 有效，当在字符串中使用多重数组时，一定要用括号将它括起来
 echo "This works: {$arr['foo'][3]}";

 // 有效
 echo "This works: " . $arr['foo'][3];

 echo "This works too: {$obj->values[3]->name}";

 echo "This is the value of the var named $name: {${$name}}";

 echo "This is the value of the var named by the return value of getName():
 {${getName()}}";

 echo "This is the value of the var named by the return value of
 \$object->getName(): {${$object->getName()}}";

 // 无效，输出： This is the return value of getName(): {getName()}
 echo "This is the return value of getName(): {getName()}";
 ?>

也可以在字符串中用变量来调用类的属性。

.. code-block:: php

 <?php
  class foo {
      var $bar = 'I am bar.';
  }

  $foo = new foo();
  $bar = 'bar';
  $baz = array('foo', 'bar', 'baz', 'quux');
  echo "{$foo->$bar}\n";
  echo "{$foo->$baz[1]}\n";
 ?>

以上例程会输出::

 I am bar.
 I am bar.

.. note:: 函数、行为、类的静态变量和类的常量只有在PHP 5以后才可在 {$} 中使用。然而，只有在用返回的值作为名 称的变量存在的情况下才会进行处理，只单一使用花括号 ({}) 无法处理从函数或行为的返回值或从类的常量或静态变量的返 回值。

.. code-block:: php

 <?php
 // 显示所有错误
 error_reporting(E_ALL);

 class beers {
    const softdrink = 'rootbeer';
    public static $ale = 'ipa';
 }

 $rootbeer = 'A & W';
 $ipa = 'Alexander Keith\'s';

 // 有效，输出： I'd like an A & W
 echo "I'd like an {${beers::softdrink}}\n";

 // 也有效，输出： I'd like an Alexander Keith's
 echo "I'd like an {${beers::$ale}}\n";
 ?>

存取和修改字符串中的字符
-------------------------

字符串中的字符可以通过一个以0为开始的，用类似数组结构中的方括号包含对应的数字来查找和修改，比如 $str[42]， 可以把 字符串想像数组 。 函数 substr() 和 substr_replace()可以用来实现多于一个字符 的情况。

.. note:: 字符串为了同样的目的也可以用花括号，比如 $str{42}，但是， 在 PHP 5.3.0中不推荐使用这种格式，应该用方括号，就像 $str[42]。

.. warning:: 方括号中的数字超出范围将会产生空白。非整数类型被转换成整数，非整数类型转变成整数，非法类型会产生一个 E_NOTICE级别错误，负数在写入时会产生一个E_NOTICE，但读 取的是空字符串。被指定的字符串只有第一个字符可用，空字符串用指定为空字节。下面为英文原文： Writing to an out of range offset pads the string with spaces. Non-integer types are converted to integer. Illegal offset type emits E_NOTICE. Negative offset emits E_NOTICE in write but reads empty string. Only the first character of an assigned string is used. Assigning empty string assigns NUL byte.

例 #8 一些字符串例子

.. code-block:: php

 <?php
 // 取得字符串的第一个字符
 $str = 'This is a test.';
 $first = $str[0];

 // 取得字符串的第三个字符
 $third = $str[2];

 // 取得字符串的最后一个字符
 $str = 'This is still a test.';
 $last = $str[strlen($str)-1]; 

 // 修改字符串的最后一个字符
 $str = 'Look at the sea';
 $str[strlen($str)-1] = 'e';

 ?>

.. note:: 用 [] 或 {} 存取其它类型的变量只会返回 NULL.

有用的函数和操作符
-------------------

字符串可以用'.' (点) 操作符连接起来， 注意 '+' (加号) 操作符 没有 这个功能。 更多信息参考 字符串操作符 。

对于字符串 的操作有很多有用的函数。

可以参考 字符串函数 了解大部分函数， 高级的查找&替换功能可以参考 正则表达式函数 或 Perl类型的正则 表达式函数。

另外还有URL字符串的函数， 也有加密/解密字符串的函数。 (mcrypt 和 mhash).

最后，可以参考 字符类型函数。

转换成字符串
-------------

一个值可以通过在其前面加上(string)或用 strval()函数来转变成 字符串。 在一个需要字符串的表达式中，字符串会自动转变，比如在使用函数 echo 或 print 时， 或在一个变量和一个 字符串 进行比较时，就会发生这种转变 类型 和 类型转换 可以更好的解释下面的事情，也可参考函 数 settype() 。

一个boolean TRUE 值被转换成 字符串"1"。 Boolean FALSE 被转换成"" (空的字符串)。 这种转变可以在 boolean 和 字符串 之间往返进行。

一个 整数 或 浮点数 被转变为数字的字面样式的字符串 (包括 浮点数中的指数部分)，使用指数计数法的浮点数 (4.1E+6)也可转变。

.. note:: 在脚本场所(category LC_NUMERIC)定义了小数点，更多可以参考函数 setlocale()。

数组转换成 字符串 "Array"，因此， echo 和 print c无法显示出该数组的值。如果显示一个数组值，可以用 echo $arr['foo']这种结构，更多内容见下文。

在PHP 4中对象被转换成 字符串 "Object"， 果为了调试原因需要打印出对象的值，方法见正文。为了得到对象的类的名称，可以用 get_class() 函数。 在PHP5中， 可以用 __toString 。

资源总会被转变成"Resource id #1"这种结构的 字符串 ， 其中的 1 是PHP分配给该资源的独特数字。不用过多关注这种结构，它马上要转变了。为了得到一个 resource类型，可以用函数 get_resource_type()。

NULL 总是被转变成空的字符串。

如上面所说的，直接把数组， 对象或 资源 转换成 字符串 不会得到超出其自身的更多信息。可以使用函数 print_r() 和 var_dump() 列出这些类型的内容。

大部分的PHP值可以转变成 字符串s 来长期储存，这被称作串行化，可以用函数 serialize() 来实现。 如果PHP引擎设定支持 WDDX ， PHP值也可储存成XML格式。

字符串转变成数字
-----------------

当一个字符串 被用在了一个数字的环境中，结果和类型如下：

如果字符串 没有包含 '.'，'e'或'E' 并且数字值符合整数类型的限定 ( PHP_INT_MAX定义的)， 这个 字符串 可被认定是一个 integer， 在其它情况下被认定为一个float。

字符串的开始部分给定了它的值，如果 字符串 以合法的数字开始，这个数字可直接使用。 否则，值就 是 0 (零)。 合法数值由符号，后面跟着一个或多个数字（可能有个小数点），再跟着可选的指数符号如'e' 或 'E'，后面跟着一个或多个数字。

.. code-block:: php

 <?php
 $foo = 1 + "10.5";                // $foo is float (11.5)
 $foo = 1 + "-1.3e3";              // $foo is float (-1299)
 $foo = 1 + "bob-1.3e3";           // $foo is integer (1)
 $foo = 1 + "bob3";                // $foo is integer (1)
 $foo = 1 + "10 Small Pigs";       // $foo is integer (11)
 $foo = 4 + "10.2 Little Piggies"; // $foo is float (14.2)
 $foo = "10.0 pigs " + 1;          // $foo is float (11)
 $foo = "10.0 pigs " + 1.0;        // $foo is float (11)     
 ?>

更多信息可以参考Unix手册中的strtod(3)。

本节中的示例可以通过复制/粘贴到下面的代码中来显示：

.. code-block:: php

 <?php
 echo "\$foo==$foo; type is " . gettype ($foo) . "<br />\n";
 ?>
 
不要想像在C语言中的那样，通过一个整数转换得到相应字符，使用函数 ord() 和 chr() 实现ASCII码和字符间的转换。
