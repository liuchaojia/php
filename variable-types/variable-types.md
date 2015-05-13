
# PHP变量类型


信息存储的主要方式是通过在一个PHP程序中使用一个变量。这里了解PHP变量是最重要的事情。

* 所有变量在PHP标有一个美元符号($)。

* 一个变量的值取决于最近赋给的值。

* 变量赋值使用‘=’操作符、变量左边和右边的表达式计算。

* 变量可以不需要被提前定义，使用时定义即可。

* 变量使用之前，需要分配有默认值。

* PHP可以自动地从一个类型转换成另一个类型。

* PHP变量和perl语言变量很相似。

PHP一共有八种数据类型可以供我们用来构造变量:

* **整型:** 是整数,没有小数点,像4195。
* **浮点型:** 浮点数,如3.14159或49.1。
* **布尔值:** 只有两个可能值或真或假。
* **空:** 只有一个值:空。
* **字符串类型:** 字符序列,像'PHP支持字符串操作.'
* **数组:** 有命名和索引所有值的集合。
* **对象:** 是程序员定义类的实例化，可以打包其他类型的值和属于这个类的函数。
* **资源:** 特殊变量持有引用外部资源到PHP(如数据库连接)。



前五个是简单类型,接下来的两个(数组和对象)是复合类型,这种复合类型可以打包其他任意类型的值,而不能是简单类型。我们将解释这章数据类型。数组和对象将分别解释。

## 整数:

他们是整数,没有小数点,像4195年。他们是最简单的类型。它们对应于简单的整数,正的和负的。整数可以分配给变量,或者他们可以用于表达式,像这样:

    $int_var = 12345;
    $another_int = -12345 + 12345;

整形可以是十进制整数（base 10）,八进制(base 8),十六进制(base 16)格式。默认的是十进制格式,八进制整数指定0开头,十六进制以0 x开头。

为最常见的平台,最大的整数(2 * * 31.1)(2147483647),最小的(负)整数是(2 * * 31.1)(或.-2,147,483,647)。

## 浮点型

他们就像3.14159或49.1。默认情况下浮点型打印所需的最小数量的小数。例如,以下代码:

	$many = 2.2888800;
	
	$many_2 = 2.2111200;
	
	$few = $many + $many_2;
	
	print(.$many + $many_2 = $few.);

它将会在浏览器中输出以下结果：

	2.28888 + 2.21112 = 4.5

## 布尔值


他们只有两个可能值或真或假。PHP提供了几个常量专门作为布尔值:TRUE和FALSE,可以这样使用:

    if (TRUE)
       print("This will always print");
    else
       print("This will never print");

### 解释其他类型为布尔值:


这里的规则确定没有任何值的“truth”的布尔类型:

* 如果该值是一个数字,如果完全等于零那么它为假,否则为真。
* 如果该值是一个字符串 ,如果字符串是空的(为零个字符)或字符串“0” 那么它为假, 否则为真。
* 空类型的值NULL总为假。
* 如果该值是一个数组,如果它不包含其他值那么它是假的, 否则为真。做为一个对象,包含一个值意味着一个成员变量被分配给一个值。
* 有效资源为真时(尽管一些函数, 成功返回资源时返回真不成功时将返回假)。
* 不要使用双精度值作为布尔值。


下面的每一个变量的真实值嵌入到它的名字时在下面的布尔上下文环境中运行都是TRUE。

    $true_num = 3 + 0.14159;
    $true_str = "Tried and true"
    $true_array[49] = "An array element";
    $false_array = array();
    $false_null = NULL;
    $false_num = 999 - 999;
    $false_str = "";

## 空：

空是一种特殊类型,只有一个值:空。给一个变量NULL值,只是这样分配:


    $my_var = NULL;

特殊的常量NULL类型按照惯例应该大小化，就是大小写敏感；但是你也可以使用以下方式来定义：

    $my_var = null;

一个变量被赋值为空，有以下属性:

* 它在布尔上下文的求值结果为FALSE。

* 测试使用IsSet()函数时返回FALSE。


## 字符串：

字符串:他们是字符序列,像“PHP支持字符串操作”。以下是有效的字符串的例子

    $string_1 = "This is a string in double quotes";
    $string_2 = "This is a somewhat longer, singly quoted string";
    $string_39 = "This string has thirty-nine characters";
    $string_0 = ""; // a string with zero characters

单引号字符串处理非常随便,而双引号字符串替换变量，PHP将对一些特殊的字符解析成为特定的字符序列。

    

它将会输出以下结果：

    My $variable will not print!n
    My name will print

没有在可用内存的范围内限制字符串长度,你可以定义任意长度的字符串。

如果字符串是包围在双引号(像”this")中， PHP将通过二种方式对字符进行预先处理：

某些字符序列以反斜杠(\)开始替换特殊字符。

变量名(从$开始)替换为字符串表示的值。

 转义序列替换:

* 换取新的一行由\n所代替
* 回车键由\n所代替
* 制表符由\t所代替
* $符号由\$所代替
* 双引号（“）由 \”所代替
* 单一的反斜杠由\\所代替

文档:

使用以下文档您可以将多个行分配给一个字符串变量:
	
	<?php
	
	$channel =<<<_XML_
	<channel>
	<title>What's For Dinner<title>
	<link>http://menu.example.com/<link>
	<description>Choose what to eat tonight.</description>
	</channel>
	_XML_;
	
	echo <<<END
	This uses the "here document" syntax to output
	multiple lines with variable interpolation. Note
	that the here document terminator must appear on a
	line with just a semicolon. no extra whitespace!
	<br />
	END;
	
	print $channel;
	?>


它将会输出以下结果：
	
	This uses the "here document" syntax to output
	multiple lines with variable interpolation. Note
	that the here document terminator must appear on a
	line with just a semicolon. no extra whitespace!
	
	<channel>
	<title>What's For Dinner<title>
	<link>http://menu.example.com/<link>
	<description>Choose what to eat tonight.</description>

## 变量范围:

声明它的程序时范围可以定义为可用性变量的范围。PHP变量可以是四种空间类型中的一个:

* 局部变量
* 函数参数
* 全局变量
* 静态变量
	
## 变量的命名规则

变量的命名规则是:

* 变量名必须以字母或下划线 "_" 开头。 
* 变量名只能包含字母数字字符以及下划线。 但你不能使用字符+、-、%(,)&等。

变量没有大小限制。