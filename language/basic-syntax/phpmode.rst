从 HTML 中分离
=========================

当 PHP 解析一个文件时，会寻找开始和结束标记，标记告诉 PHP 开始和停止解释其中的代码。此种方式的解析可以使 PHP 嵌入到各种不同的文档中，凡是在一对开始和结束标记之外的内容都会被 PHP 解析器忽略。大多数情况下 PHP 都是嵌入在 HTML 文档中的，如下例所示::

 <p>This is going to be ignored.</p>
 <?php echo 'While this is going to be parsed.'; ?>
 <p>This will also be ignored.</p>

还可以用更高级的结构：

Example #1 高级分离术

.. code-block:: php

 <?php
 if ($expression) {
    ?>
    <strong>This is true.</strong>
    <?php
 } else {
    ?>
    <strong>This is false.</strong>
    <?php
 }
 ?>

上例可正常工作，因为当 PHP 碰到结束标记 ?> 时，就简单地将其后的内容原样输出（ 除非其后紧接着一个新行,参见指令分隔符 )直到碰到下一个开始标记为止。当然，上面的例子很做作，但是对输出大块的文本而言，脱离 PHP 解析模式通常比将所有内容用 echo 或者 print 输出更有效率。

可以在 PHP 中使用四对不同的开始和结束标记。其中两种，<?php ?> 和 <script language="php"> </script> 总是可用的。另两种是短标记和 ASP 风格标记，可以在 php.ini 配置文件中打开或关闭。尽管有些人觉得短标记和 ASP 风格标记很方便，但移植性较差，通常不推荐。

.. Note:: 此外注意如果将 PHP 嵌入到 XML 或 XHTML 中则需要使用 <?php ?> 以保持符合标准。

Example #2 PHP 开始和结束标记::


 1.  <?php echo 'if you want to serve XHTML or XML documents, do like this'; ?>

 2.  <script language="php">
        echo 'some editors (like FrontPage) don\'t
              like processing instructions';
     </script>

 3.  <? echo 'this is the simplest, an SGML processing instruction'; ?>
     <?= expression ?> This is a shortcut for "<? echo expression ?>"

 4.  <% echo 'You may optionally use ASP-style tags'; %>
     <%= $variable; # This is a shortcut for "<% echo . . ." %>

上例中的 1 和 2 总是可用的，其中 1 是最常用，并建议使用的。

短标记（上例 3）仅在通过 php.ini 配置文件中的指令 short_open_tag 打开后才可用，或者在 PHP 编译时加入了 --enable-short-tags 选项。

ASP 风格标记（上例 4）仅在通过 php.ini 配置文件中的指令 asp_tags 打开后才可用。

.. Note:: 在以下情况应避免使用短标记：开发需要发行的程序或者库，或者在用户不能控制的服务器上开发。因为目标服务器可能不支持短标记。为了代码的移植及发行，确保不要使用短标记。
