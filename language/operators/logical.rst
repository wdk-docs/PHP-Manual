逻辑运算符
============================

逻辑运算符
例子	名称	结果
$a and $b	And（逻辑与）	TRUE，如果 $a 与 $b 都为 TRUE。
$a or $b	Or（逻辑或）	TRUE，如果 $a 或 $b 任一为 TRUE。
$a xor $b	Xor（逻辑异或）	TRUE，如果 $a 或 $b 任一为 TRUE，但不同时是。
! $a	Not（逻辑非）	TRUE，如果 $a 不为 TRUE。
$a && $b	And（逻辑与）	TRUE，如果 $a 与 $b 都为 TRUE。
$a || $b	Or（逻辑或）	TRUE，如果 $a 或 $b 任一为 TRUE。
“与”和“或”有两种不同形式运算符的原因是它们运算的优先级不同（见运算符优先级）。

Example #1 逻辑运算符示例
<?php

// 下面的 foo() 不会被调用，因为它们被运算符“短路”了。
$a = (false && foo());
$b = (true  || foo());
$c = (false and foo());
$d = (true  or  foo());

// "||" 的优先级比 "or" 高
$e = false || true; // $e 被赋值为 (false || true)，结果为 true
$f = false or true; // $f 被赋值为 false [Altair注："=" 的优先级比 "or" 高]
var_dump($e, $f);

// "&&" 的优先级比 "and"　高
$g = true && false; // $g 被赋值为 (true && false)，结果为 false
$h = true and false; // $h 被赋值为 true [Altair注："=" 的优先级比 "and" 高]
var_dump($g, $h);
?>
以上例程的输出类似于：
bool(true)
bool(false)
bool(false)
bool(true)
