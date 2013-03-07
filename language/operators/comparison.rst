比较运算符
============================

比较运算符，如同它们名称所暗示的，允许对两个值进行比较。还可以参考 PHP 类型比较表看不同类型相互比较的例子。

比较运算符
例子	名称	结果
$a == $b	等于	TRUE，如果 $a 等于 $b。
$a === $b	全等	TRUE，如果 $a 等于 $b，并且它们的类型也相同。（PHP 4 引进）
$a != $b	不等	TRUE，如果 $a 不等于 $b。
$a <> $b	不等	TRUE，如果 $a 不等于 $b。
$a !== $b	非全等	TRUE，如果 $a 不等于 $b，或者它们的类型不同。（PHP 4 引进）
$a < $b	小与	TRUE，如果 $a 严格小于 $b。
$a > $b	大于	TRUE，如果 $a 严格 $b。
$a <= $b	小于等于	TRUE，如果 $a 小于或者等于 $b。
$a >= $b	大于等于	TRUE，如果 $a 大于或者等于 $b。
如果比较一个整数和字符串，则字符串会被转换为整数。如果比较两个数字字符串，则作为整数比较。此规则也适用于 switch 语句。

<?php
var_dump(0 == "a"); // 0 == 0 -> true
var_dump("1" == "01"); // 1 == 1 -> true
var_dump("1" == "1e0"); // 1 == 1 -> true
switch ("a") {
case 0:
    echo "0";
    break;
case "a": // never reached because "a" is already matched with 0
    echo "a";
    break;
}
?>
对于多种类型，比较运算符根据下表比较（按顺序）。

比较多种类型
运算数 1 类型	运算数 1 类型	结果
null 或 string	string	将 NULL 转换为 ""，进行数字或词汇比较
bool 或 null	任何其它类型	转换为 bool，FALSE < TRUE
object	object	 内置类可以定义自己的比较，不同类不能比较，相同类和数组同样方式比较属性（PHP 4 中），PHP 5 有其自己的说明
string，resource 或 number	string，resource 或 number	将字符串和资源转换成数字，按普通数学比较
array	array	 具有较少成员的数组较小，如果运算数 1 中的键不存在于运算数 2 中则数组无法比较，否则挨个值比较（见下例）
array	任何其它类型	array 总是更大
object	任何其它类型	object 总是更大
Example #1 标准数组比较代码
<?php
// 数组是用标准比较运算符这样比较的
function standard_array_compare($op1, $op2)
{
    if (count($op1) < count($op2)) {
        return -1; // $op1 < $op2
    } elseif (count($op1) > count($op2)) {
        return 1; // $op1 > $op2
    }
    foreach ($op1 as $key => $val) {
        if (!array_key_exists($key, $op2)) {
            return null; // uncomparable
        } elseif ($val < $op2[$key]) {
            return -1;
        } elseif ($val > $op2[$key]) {
            return 1;
        }
    }
    return 0; // $op1 == $op2
}
?>
参见 strcasecmp()， strcmp()，数组运算符和类型一章。

三元运算符

另一个条件运算符是“?:”（或三元）运算符 。

Example #2 赋默认值
<?php
 // Example usage for: Ternary Operator
 $action = (empty($_POST['action'])) ? 'default' : $_POST['action'];

 // The above is identical to this if/else statement
 if (empty($_POST['action'])) {
     $action = 'default';
 } else {
     $action = $_POST['action'];
 }

 ?>
表达式 (expr1) ? (expr2) : (expr3) 在 expr1 求值为 TRUE 时的值为 expr2，在 expr1 求值为 FALSE 时的值为 expr3。
Note: 注意三元运算符是个语句，因此其求值不是变量，而是语句的结果。如果想通过引用返回一个变量这点就很重要。在一个通过引用返回的函数中语句 return $var == 42 ? $a : $b; 将不起作用，以后的 PHP 版本会为此发出一条警告。

Note:

建议避免将三元运算符堆积在一起使用。当在一条语句中使用多个三元运算符时会造成 PHP 运算结果不清晰： Is is recommended that you avoid "stacking" ternary expressions. PHP's behaviour when using more than one ternary operator within a single statement is non-obvious:

Example #3 不清晰的三元运算符行为
<?php
// 乍看起来下面的输出是 'true'
echo (true?'true':false?'t':'f');

// 然而，上面语句的实际输出是't'，因为三元运算符是从左往右计算的

// 下面是与上面等价的语句，但更清晰
echo ((true ? 'true' : 'false') ? 't' : 'f');

// here, you can see that the first expression is evaluated to 'true', which
// in turn evaluates to (bool)true, thus returning the true branch of the
// second ternary expression.
?>
