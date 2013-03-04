来自 PHP 之外的变量
====================

HTML 表单（GET 和 POST）

当一个表单体交给 PHP 脚本时，表单中的信息会自动在脚本中可用。有很多方法访问此信息，例如：

Example #1 一个简单的 HTML 表单
<form action="foo.php" method="POST">
    Name:  <input type="text" name="username"><br />
    Email: <input type="text" name="email"><br />
    <input type="submit" name="submit" value="Submit me!" />
</form>
根据特定的设置和个人的喜好，有很多种方法访问 HTML 表单中的数据。例如：

Example #2 从一个简单的 POST HTML 表单访问数据
<?php
// 自 PHP 4.1.0 起可用
   echo $_POST['username'];
   echo $_REQUEST['username'];
   
   import_request_variables('p', 'p_');
   echo $p_username;
// PHP 6以后将无效。自 PHP 5.0.0 起，这些较长的预定义变量
// 可用 register_long_arrays 指令关闭。

   echo $HTTP_POST_VARS['username'];

// 如果 PHP 指令 register_globals = on 时可用。不过自
// PHP 4.2.0 起默认值为 register_globals = off。
// 不提倡使用/依赖此种方法。

   echo $username;
?>
使用 GET 表单也类似，只不过要用适当的 GET 预定义变量。GET 也适用于 QUERY_STRING（URL 中在“?”之后的信息）。因此，举例说，http://www.example.com/test.php?id=3 包含有可用 $_GET['id'] 访问的 GET 数据。参见 $_REQUEST 和 import_request_variables()。

Note:

超全局数组和 $_POST 以及 $_GET 一样，自 PHP 4.1.0 起可用。

如上所示，在 PHP 4.2.0 之前 register_globals 的默认值是 on。PHP 社区鼓励大家不要依赖此指令，建议在编码时假定其为 off。

Note:

magic_quotes_gpc 配置指令影响到 Get，Post 和 Cookie 的值。如果打开，值 (It's "PHP!") 会自动转换成 (It\'s \"PHP!\")。数据库的插入就需要转义。参见 addslashes()， stripslashes() 和 magic_quotes_sybase。

PHP 也懂得表单变量上下文中的数组（参见相关常见问题）。例如可以将相关的变量编成组，或者用此特性从多选输入框中取得值。例如，将一个表单 POST 给自己并在提交时显示数据：

Example #3 更复杂的表单变量
<?php
if (isset($_POST['action']) && $_POST['action'] == 'submitted') {
    echo '<pre>';

    print_r($_POST);
    echo '<a href="'. $_SERVER['PHP_SELF'] .'">Please try again</a>';

    echo '</pre>';
} else {
?>
<form action="<?php echo $_SERVER['PHP_SELF']; ?>" method="post">
    Name:  <input type="text" name="personal[name]"><br />
    Email: <input type="text" name="personal[email]"><br />
    Beer: <br>
    <select multiple name="beer[]">
        <option value="warthog">Warthog</option>
        <option value="guinness">Guinness</option>
        <option value="stuttgarter">Stuttgarter Schwabenbr</option>
    </select><br />
    <input type="hidden" name="action" value="submitted" />
    <input type="submit" name="submit" value="submit me!" />
</form>
<?php
}
?>
IMAGE SUBMIT 变量名

当提交表单时，可以用一幅图像代替标准的提交按钮，用类似这样的标记：

<input type="image" src="image.gif" name="sub" />
当用户点击到图像中的某处时，相应的表单会被传送到服务器，并加上两个变量 sub_x 和 sub_y。它们包含了用户点击图像的坐标。有经验的用户可能会注意到被浏览器发送的实际变量名包含的是一个点而不是下划线（即 sub.x 和 sub.y），但 PHP 自动将点转换成了下划线。

HTTP Cookies

PHP 透明地支持 » RFC 6265定义中的 HTTP cookies。Cookies 是一种在远端浏览器端存储数据并能追踪或识别再次访问的用户的机制。可以用 setcookie() 函数设定 cookies。Cookies 是 HTTP 信息头中的一部分，因此 SetCookie 函数必须在向浏览器发送任何输出之前调用。对于 header() 函数也有同样的限制。Cookie 数据会在相应的 cookie 数据数组中可用，例如 $_COOKIE，$HTTP_COOKIE_VARS 和 $_REQUEST。更多细节和例子见 setcookie() 手册页面。

如果要将多个值赋给一个 cookie 变量，必须将其赋成数组。例如：

<?php
  setcookie("MyCookie[foo]", 'Testing 1', time()+3600);
  setcookie("MyCookie[bar]", 'Testing 2', time()+3600);
?>
这将会建立两个单独的 cookie，尽管 MyCookie 在脚本中是一个单一的数组。如果想在仅仅一个 cookie 中设定多个值，考虑先在值上使用 serialize() 或 explode()。

注意在浏览器中一个 cookie 会替换掉上一个同名的 cookie，除非路径或者域不同。因此对于购物车程序可以保留一个计数器并一起传递，例如：

Example #4 一个 setcookie() 的示例
<?php
if (isset($_COOKIE['count'])) {
    $count = $_COOKIE['count'] + 1;
} else {
    $count = 1;
}
setcookie('count', $count, time()+3600);
setcookie("Cart[$count]", $item, time()+3600);
?>
变量名中的点

通常，PHP 不会改变传递给脚本中的变量名。然而应该注意到点（句号）不是 PHP 变量名中的合法字符。至于原因，看看：

<?php
$varname.ext;  /* 非法变量名 */
?>
这时，解析器看到是一个名为 $varname 的变量，后面跟着一个字符串连接运算符，后面跟着一个裸字符串（即没有加引号的字符串，且不匹配任何已知的健名或保留字）'ext'。很明显这不是想要的结果。
出于此原因，要注意 PHP 将会自动将变量名中的点替换成下划线。

确定变量类型

因为 PHP 会判断变量类型并在需要时进行转换（通常情况下），因此在某一时刻给定的变量是何种类型并不明显。PHP 包括几个函数可以判断变量的类型，例如： gettype()， is_array()， is_float()， is_int()， is_object() 和 is_string()。参见类型一章。
