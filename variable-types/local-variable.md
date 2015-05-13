# PHP局部变量

声明它的程序时范围可以定义为可用性变量的范围。PHP变量可以是四种空间类型中的一个:

* 局部变量
* 函数参数
* 全局变量
* 静态变量

## 局部变量

一个变量在函数中声明时被认为是局部的;也就是说,它可以在函数内部被引用。函数以外的任何赋值将被认为是一个完全不同的变量:
 
	<?
	$x = 4;
	function assignx () {
	$x = 0;
	print "\$x inside function is $x. 
	";
	}
	assignx();
	print "\$x outside of function is $x. 
	";
	?>
	This will produce following result.

这将会产生以下结果：

	$x inside function is 0.
	$x outside of function is 4.
	
