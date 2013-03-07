数组运算符
============================

数组运算符
例子	名称	结果
$a + $b	联合	$a 和 $b 的联合。
$a == $b	相等	如果 $a 和 $b 具有相同的键／值对则为 TRUE。
$a === $b	全等	如果 $a 和 $b 具有相同的键／值对并且顺序和类型都相同则为 TRUE。
$a != $b	不等	如果 $a 不等于 $b 则为 TRUE。
$a <> $b	不等	如果 $a 不等于 $b 则为 TRUE。
$a !== $b	不全等	如果 $a 不全等于 $b 则为 TRUE。
+ 运算符把右边的数组元素（除去键值与左边的数组元素相同的那些元素）附加到左边的数组后面，但是重复的键值不会被覆盖。

<?php
$a = array("a" => "apple", "b" => "banana");
$b = array("a" => "pear", "b" => "strawberry", "c" => "cherry");

$c = $a + $b; // Union of $a and $b
echo "Union of \$a and \$b: \n";
var_dump($c);

$c = $b + $a; // Union of $b and $a
echo "Union of \$b and \$a: \n";
var_dump($c);
?>
执行后，此脚本会显示：
Union of $a and $b:
array(3) {
  ["a"]=>
  string(5) "apple"
  ["b"]=>
  string(6) "banana"
  ["c"]=>
  string(6) "cherry"
}
Union of $b and $a:
array(3) {
  ["a"]=>
  string(4) "pear"
  ["b"]=>
  string(10) "strawberry"
  ["c"]=>
  string(6) "cherry"
}
数组中的单元如果具有相同的键名和值则比较时相等。

Example #1 比较数组
<?php
$a = array("apple", "banana");
$b = array(1 => "banana", "0" => "apple");

var_dump($a == $b); // bool(true)
var_dump($a === $b); // bool(false)
?>
参见数组类型和数组函数章节。
