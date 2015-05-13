# PHP函数


PHP函数类似于其他编程语言。函数是一段代码将以输入参数的形式做一些处理操作,并返回一个值。

你已经见过许多函数例如fopen()和fread()等。他们都是内置函数,但你可以自己选择创建自己的函数。

你应该清楚两个部分: 　


* 创建一个PHP函数
* 调用一个PHP函数


事实上,你几乎不需要创建自己的PHP函数,因为已经有超过1000个的内置库函数在不同的区域被创建,你只需要根据您的需求调用他们。

请参阅一套完整的有用的PHP Function Reference函数。

## 创建PHP函数:
它非常容易创建自己的PHP函数。假设您希望创建一个PHP函数, 当你调用它时，只需编写一个简单的消息显示在你的浏览器上面,。以下示例创建了一个名为writeMessage()的函数, 只是在创建它之后调用它。

注意,在创建一个函数的名字时应该在开头使用关键字 function并且把所有的PHP代码放在{and}括号内。如下面的例子所示:

	<html>
	<head>
	<title>Writing PHP Function</title>
	</head>
	<body>
	
	<?php
	/* Defining a PHP Function */
	function writeMessage()
	{
	  echo "You are really a nice person, Have a nice time!";
	}
	/* Calling a PHP Function */
	writeMessage();
	?>
	</body>
	</html>    
    
这将显示以下结果:
	You are really a nice person, Have a nice time!
## PHP函数的参数

PHP给你选择往函数里传递参数。你可以传递多个参数。这些参数的工作方式就像你的函数里面内部变量。以下示例有两个整数参数,并将它们添加在一起,然后打印。
	
	<html>
	<head>
	<title>Writing PHP Function with Parameters</title>
	</head>
	<body>
	
	<?php
	function addFunction($num1, $num2)
	{
	  $sum = $num1 + $num2;
	  echo "Sum of the two numbers is : $sum";
	}
	addFunction(10, 20);
	?>
	</body>
	</html>

这将显示以下结果:
	Sum of the two numbers is : 30
## 按引用传递参数
可以将参数作为引用传递给函数。这意味着函数可以操作变量引用,而不是对一个变量值的副本的操作。
在这些情况下一个参数的任何变化都会改变原来的变量的值。您可以通过在变量名称前加&符号传递一个参数引用变量，在函数调用时或函数定义时。

下面的例子描述了这两个情况。

	<html>
	<head>
	<title>Passing Argument by Reference</title>
	</head>
	<body>
	<?php
	function addFive($num)
	{
	   $num += 5;
	}
	
	function addSix(&$num)
	{
	   $num += 6;
	}
	$orignum = 10;
	addFive( &$orignum );
	echo "Original Value is $orignum<br />";
	addSix( $orignum );
	echo "Original Value is $orignum<br />";
	?>
	</body>
	</html>


这将显示以下结果:

	Original Value is 15
	Original Value is 21
## PHP函数返回值
一个函数可以使用返回语句返回一个值与对象。函数返回值时会停止执行return语句后代码并将值返回给调用的代码。

你可以使用return array(1,2,3,4)从一个函数返回多个值。

以下示例有两个整数参数,并将它们添加在一起,然后返回调用程序的总和。注意,return关键字用于从一个函数返回一个值。

	<html>
	<head>
	<title>Writing PHP Function which returns value</title>
	</head>
	<body>
	
	<?php
	function addFunction($num1, $num2)
	{
	  $sum = $num1 + $num2;
	  return $sum;
	}
	$return_value = addFunction(10, 20);
	echo "Returned value from the function : $return_value";
	?>
	</body>
	</html>

这将显示以下结果:

	Returned value from the function : 30
## 设置函数参数的默认值:
如果函数的调用者没有传递值给这个参数，你可以设置默认值给这个参数。

函数输出空,以防没有任何参数值传递给这个函数。

	<html>
	<head>
	<title>Writing PHP Function which returns value</title>
	</head>
	<body>
	
	<?php
	function printMe($param = NULL)
	{
	   print $param;
	}
	printMe("This is test");
	printMe();
	?>
	
	</body>
	</html>
这将显示以下结果:

	This is test

## 动态函数调用:
可以分配函数名给一个字符串变量,然后将这些变量指向函数名称本身。下面的例子描述了这种行为。

	<html>
	<head>
	<title>Dynamic Function Calls</title>
	</head>
	<body>
	<?php
	function sayHello()
	{
	   echo "Hello<br />";
	}
	$function_holder = "sayHello";
	$function_holder();
	?>
	</body>
	</html>
这将显示以下结果:

	Hello