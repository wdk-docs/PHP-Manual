递增／递减运算符
============================

PHP 支持 C 风格的前／后递增与递减运算符。

Note: 递增／递减运算符不影响布尔值。递减 NULL 值也没有效果，但是递增 NULL 的结果是 1。

递增／递减运算符
例子	名称	效果
++$a	前加	$a 的值加一，然后返回 $a。
$a++	后加	返回 $a，然后将 $a 的值加一。
--$a	前减	$a 的值减一， 然后返回 $a。
$a--	后减	返回 $a，然后将 $a 的值减一。
一个简单的示例脚本：

<?php
echo "<h3>Postincrement</h3>";
$a = 5;
echo "Should be 5: " . $a++ . "<br />\n";
echo "Should be 6: " . $a . "<br />\n";

echo "<h3>Preincrement</h3>";
$a = 5;
echo "Should be 6: " . ++$a . "<br />\n";
echo "Should be 6: " . $a . "<br />\n";

echo "<h3>Postdecrement</h3>";
$a = 5;
echo "Should be 5: " . $a-- . "<br />\n";
echo "Should be 4: " . $a . "<br />\n";

echo "<h3>Predecrement</h3>";
$a = 5;
echo "Should be 4: " . --$a . "<br />\n";
echo "Should be 4: " . $a . "<br />\n";
?>
在处理字符变量的算数运算时，PHP 沿袭了 Perl 的习惯，而非 C 的。例如，在 Perl 中 'Z'+1 将得到 'AA'，而在 C 中，'Z'+1 将得到 '['（ord('Z') == 90，ord('[') == 91）。注意字符变量只能递增，不能递减，并且只支持纯字母（a-z 和 A-Z）。

Example #1 涉及字符变量的算数运算
<?php
$i = 'W';
for ($n=0; $n<6; $n++) {
    echo ++$i . "\n";
}
?>
以上例程会输出：
X
Y
Z
AA
AB
AC
递增或递减布尔值没有效果。
