# PHP Function Parameters

声明它的程序时范围可以定义为可用性变量的范围。PHP变量可以是四种空间类型中的一个:

* 局部变量
* 函数参数
* 全局变量
* 静态变量

**注意:**PHP函数将在PHP函数章节详细介绍。

但是简短的函数是一个小单位的程序，它可以采取输入参数的形式之后做一些处理，可能返回一个值。

## 函数参数
 
函数参数声明在函数名之后括号内。他们就像一个典型的变量声明:
	
	<?
	// multiply a value by 10 and return it to the caller
	function multiply ($value) {
	    $value = $value * 10;
	    return $value;
	}
	
	$retval = multiply (10);
	Print "Return value is $retval\n";
	?>

这将会输出以下结果：

	Return value is 100

    


