
# PHP 字符串

PHP的字符序列,像“PHP支持字符串操作”。

**注意:** 是PHP提供了内置字符串函数引用库。

下面的例子是有效的定义字符串的例子

    $string_1 = "This is a string in double quotes";
    $string_2 = "This is a somewhat longer, singly quoted string";
    $string_39 = "This string has thirty-nine characters";
    $string_0 = ""; // a string with zero characters

单引号串和双引号串在PHP中的处理是不相同的。双引号串中的内容可以被解释而且替换，而单引号串中的内容总被认为是普通字符。例如：
    

上述代码将会输出以下代码：

    My $variable will not print!n
    My name will print

字符串在可用内存的范围内没有长度的限制，你应该能够定义任意长度的字符串。

字符串被双引号(像“this”)分割，在以下两个方面由PHP预处理:

* 某些以反斜杠(\)字符序列开始的被替换为特殊字符。
* 变量名(从美元$开始)替换为字符串表示的值。

The escape-sequence replacements are:

* n is replaced by the newline character
* r is replaced by the carriage-return character
* t is replaced by the tab character
* $ is replaced by the dollar sign itself ($)
* " is replaced by a single double-quote (")
* \ is replaced by a single backslash ()
转义序列替换:

* 换取新的一行由\n所代替
* 回车键由\n所代替
* 制表符由\t所代替
* ($)符号由\$所代替
* 双引号（“）由 \”所代替
* 单一的反斜杠(\)由\\所代替

## 字符串并置运算符

要把两个变量连接在一起，请使用这个点运算符 (.) ：

	<?php
	$txt1="Hello World";
	$txt2="1234";
	echo $txt1 . " " . $txt2;
	?>

以上代码会输出以下结果：

    Hello World 1234

您可以看到，我们在上面的例子中使用了两次并置运算符。这是由于我们需要插入第三个字符串。

两个字符串变量之间我们添加了一个字符串和一个字符,一个空格分开了两个变量。


## 使用 strlen() 函数

strlen() 函数用于计算字符串的长度。
让我们算出字符串 "Hello world!" 的长度：
	
	<?php
	echo strlen("Hello world!");
	?>
以上代码的输出：

    12

字符串的长度信息常常用在循环或其他函数中，因为那时确定字符串何时结束是很重要的（例如，在循环中，我们需要在字符串中的最后一个字符之后结束循环）。

## 使用strpos()函数

strpos() 函数用于在字符串内检索一段字符串或一个字符。

如果在字符串中找到匹配，该函数会返回第一个匹配的位置。如果未找到匹配，则返回 FALSE。

让我们试一下，是不是能在字符串中找到子字符串 "world"：

	<?php
	echo strpos("Hello world!","world");
	?> 
以上代码的输出是： 

    6

正如您看到的，在我们的字符串中，字符串 "world" 的位置是 6。返回 6 而不是 7，是由于字符串中的首个位置的 0，而不是 1。
