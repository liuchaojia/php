# PHP 循环类型

PHP 中的循环语句用于执行指定次数相同的代码块。PHP支持以下四种循环类型：

* **for -** 循环执行代码块指定的次数 
* **while -** 只要指定的条件为真，则循环执行代码块 
* **do...while -** 循环执行代码块，然后在指定的条件为真时重复这个循环 
* **foreach -** 根据数组中每个元素来循环代码块 

我们将讨论关于关键字**continue**和**break**在循环执行结构中的使用。


The for statement is used when you know how many times you want to execute a statement or a block of statements.



Loops in PHP are used to execute the same block of code a specified number of times. PHP supports following four loop types.

* **for -** loops through a block of code a specified number of times.
* **while -** loops through a block of code if and as long as a specified condition is true.
* **do...while -** loops through a block of code once, and then repeats the loop as long as a special condition is true.
* **foreach -** loops through a block of code for each element in an array.

We will discuss about **continue** and **break** keywords used to control the loops execution.

## for 语句

当您已经确定了代码块的重复执行次数，for 语句可以被使用。

## 语法

    for (initialization; condition; increment)
    {
        code to be executed;
    }

初始化程序是用来设置循环次数的初始值。为了这个目的变量可能会在这里被声明,这是传统的命名方式$i。



## 例子

下面的例子使二个被赋值的变量会在每次循环中输出，并且循环五次:

	<html>
	<body>
	<?php
	$a = 0;
	$b = 0;
	
	for( $i=0; $i<5; $i++ )
	{
	    $a += 10;
	    $b += 5;
	}
	echo ("At the end of the loop a=$a and b=$b" );
	?>
	</body>
	</html>

这将会输出以下结果：


    At the end of the loop a=50 and b=25

## while 循环语句
只要指定的条件为真，while 语句将重复执行代码块。

如果表达式条件为真,那么代码块将被执行。然后执行表达式测试代码，表达式的循环将继续执行,直到发现是假的才结束循环体。

## 语法




    while (condition)
    {
        code to be executed;
    }

## 例子

这个例子将一个变量循环十次，每次循环值会自增或自减,直到循环到10当条件是假时,循环才结束。

	<html>
	<body>
	<?php
	$i = 0;
	$num = 50;
	
	while( $i < 10)
	{
	   $num--;
	   $i++;
	}
	echo ("Loop stopped at i = $i and num = $num" );
	?>
	</body>
	</html>

上述代码将会输出以下代码：

    Loop stopped at i = 10 and num = 40

## do_while 循环语句

do...while 语句会至少执行一次代码 - 然后，只要条件为真，就会重复进行循环。

### 语法

	do
	{
	code to be executed;
	}
    while (condition); 
### 例子
下面的例子将对 变量i 的值进行一次累加，然后，只要 i 小于 10 的条件为真，就会继续累加下去：

	<html>
	<body>
	<?php
	$i = 0;
	$num = 0;
	do
	{
	  $i++;
	}while( $i < 10 );
	echo ("Loop stopped at i = $i" );
	?>
	</body>
	</html>

上述代码将会输出以下代码：
	
	Loop stopped at i = 10
	
## foreach 语句
foreach 语句用于循环遍历数组。每进行一次循环，当前数组元素的值就会被赋值给 value 变量，数组指针会逐一地移动以此类推。
### 语法

	foreach (array as value)
	{
	    code to be executed;
	}
### 例子

尝试以下例子来列出一个数组的值。

	<html>
	<body>
	<?php
	$array = array( 1, 2, 3, 4, 5);
	foreach( $array as $value )
	{
	  echo "Value is $value <br />";
	}
	?>
	</body>
	</html>

上述代码将会输出以下代码：

	Value is 1
	Value is 2
	Value is 3
	Value is 4
	Value is 5




## Break语句

PHP 关键字break 被用来结束当前循环。

break语句坐落在语句块。如果给你完全控制,每当你想退出本次循环。立即走出一个循环语句下次循环将被执行。 

### 例子

下面的例子当值达到3条件为真的时候的时候会终止循环。

	<html>
	<body>
	
	<?php
	$i = 0;
	
	while( $i < 10)
	{
	   $i++;
	   if( $i == 3 )break;
	}
	echo ("Loop stopped at i = $i" );
	?>
	</body>
	</html>

上述代码将会输出以下代码：

	Loop stopped at i = 3

## Continue语句
PHP continue关键字在循环结构中用来跳过本次循环但它不会终止循环。 

continue语句像break语句一样坐落在包含循环执行的代码块中。通过遇到的continue关键字,跳过本次循环剩下的循环代码，执行下次循环。

### 例子
在以下示例循环输出的值是数组,但条件变为真时只是跳过本次循环，执行下次循环。

	<html>
	<body>
	<?php
	$array = array( 1, 2, 3, 4, 5);
	foreach( $array as $value )
	{
	  if( $value == 3 )continue;
	  echo "Value is $value <br />";
	}
	?>
	</body>
	</html>

上述代码将会输出以下代码：

	Value is 1
	Value is 2
	Value is 4
	Value is 5

