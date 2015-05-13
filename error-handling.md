# PHP错误和异常处理

错误处理是发现程序运行过程中出现的错误,然后采取适当的行动加以处理。如果你能妥善处理错误就可能避免许多无法预料的后果的发生。

在PHP处理一个非常简单的错误

## 使用die()函数：

当你写PHP程序时在运行之前你应该检查所有可能的错误条件并在必要时采取适当的行动

试试下面的例子，没有/ tmp /test.xt,这个文件,看产生什么错误
	<?php
	if(!file_exists("/tmp/test.txt"))
	 {
	 die("File not found");
	 }
	else
	 {
	 $file=fopen("/tmp/test.txt","r");
	 print "Opend file sucessfully";
	 }
	 // Test of the code here.
	?>

这种方式你可以编写出高效的代码。使用以上技术可以使你的程序产生错误时可以停止你的程序时并且显示更有意义的和用户友好错误信息。

## 定义自定义错误处理函数:
自定义错误报告的处理方式，你可以按照自己定义的格式打印错误报告，PHP提供了一个来定义错误处理函数框架。

这个函数能够操作至少两个参数(错误级别和错误消息),但也可以接受五个参数(可选:文件、行编号和错误上下文):

语法

	error_function(error_level,error_message, error_file,error_line,error_context); 
  
	参数          	说明
	error_level  	必需。为用户定义的错误规定错误报告级别。必须是一个值数。
	error_message	必需。为用户定义的错误规定错误消息。
	error_file	    可选。规定错误在其中发生的文件名。
	error_line   	可选。规定错误发生的行号。
	error_context	可选。规定一个数组，包含了当错误发生时在用的每个变量以及它们的值。
## 错误报告级别
这些错误报告级别是错误处理程序旨在处理的错误的不同的类型。

这些值和|运算符结合使用
	
	值	常量	                  描述
	1	E_ERROR	      致命的运行时错误。停止执行脚本
	2	E_WARNING	  非致命的运行时错误。不暂停脚本执行。
	4	E_PARSE	      编译时解析错误。解析错误只能由解析器生成。
	8	E_NOTICE	  运行时通知。脚本发现可能有错误发生，但也可能在脚本正常运行时发生。
	16	E_CORE_ERROR	致命的错误发生在PHP的初始启动。
	32	E_CORE_WARNING	非致命的运行时错误。这发生在PHP的初始启动。
	256	E_USER_ERROR	致命的用户生成的错误。这类似于程序员使用 PHP 函数 trigger_error() 设置的 E_ERROR。
	512	E_USER_WARNING	非致命的用户生成的警告。这类似于程序员使用 PHP 函数 trigger_error() 设置的 E_WARNING。
	1024	E_USER_NOTICE	用户生成的通知。这类似于程序员使用 PHP 函数 trigger_error() 设置的 E_NOTICE。
	2048	E_STRICT	运行时通知。启用PHP建议修改您的代码将确保代码的最好的互操作性和兼容性。
	4096	E_RECOVERABLE_ERROR	可捕获的致命错误。类似 E_ERROR，但可被用户定义的处理程序捕获。(参见 set_error_handler())
	8191	E_ALL	所有错误和警告，除级别 E_STRICT 以外。（在 PHP 6.0，E_STRICT 是 E_ALL 的一部分）


所有上述错误级别可以使用PHP内置库函数设置表中定义的任意值。 

	int error_reporting ( [int $level] )
下面是你可以创建一个错误处理功能:函数:

	<?php
	function handleError($errno, $errstr,$error_file,$error_line)
	{ 
	 echo "<b>Error:</b> [$errno] $errstr - $error_file:$error_line";
	 echo "<br />";
	 echo "Terminating PHP Script";
	 die();
	}
	?>

你一旦定义自定义错误处理程序，您需要使用PHP内置库set_error_handler函数来设置它。现在让我们通过调用一个不存在的函数来检查我们的示例

	<?php
	error_reporting( E_ERROR );
	function handleError($errno, $errstr,$error_file,$error_line)
	{
	 echo "<b>Error:</b> [$errno] $errstr - $error_file:$error_line";
	 echo "<br />";
	 echo "Terminating PHP Script";
	 die();
	}
	//set error handler
	set_error_handler("handleError");
	
	//trigger error
	myFunction();
	?>

## 异常处理
PHP 5 提供了一种新的面向对象的错误处理方法。异常处理非常重要,它提供了一个更好的控制错误处理机制。

可以解释这些新关键字相关的异常。

1.	Try - 使用异常的函数应该位于 "try" 代码块内。如果没有触发异常，则代码将照常继续执行。但是如果异常被触发，会抛出一个异常。 
2.	Throw - 这里规定如何触发异常。每一个 "throw" 必须对应至少一个 "catch"。 
3.	Catch - "catch" 代码块会捕获异常，并创建一个包含异常信息的对象。 

当将抛出一个异常,代码语句不会被执行后,和PHP将试图找到第一个匹配的catch代码块。如果没有捕获到异常，PHP将会发布一个致命的错误“未捕获异常……“

* 需要进行异常处理的代码应该放入 try 代码块内，以便捕获潜在的异常。 
* 每个 try 或 throw 代码块必须至少拥有一个对应的 catch 代码块。 
* 使用多个 catch 代码块可以捕获不同种类的异常。 
* 异常可以在 try 代码块内的 catch 代码块中再次抛出（re-thrown）异常。 

### 实例

下面是一段代码,复制并粘贴这段代码到一个文件中并验证结果

	<?php
	try {
	    $error = 'Always throw this error';
	    throw new Exception($error);
	
	    // Code following an exception is not executed.
	    echo 'Never executed';
	
	} catch (Exception $e) {
	    echo 'Caught exception: ',  $e->getMessage(), "\n";
	}
	
	// Continue execution
	echo 'Hello World';
	?>

在上面的例子中使用$ e - > getMessage函数得到错误消息。在使用异常类时有以下功能函数可以使用：

* getMessage()- 得到异常的消息 
* getCode() – 异常的代码块
* getFile() – 异常的源文件名称
* getLine() – 异常的文件行号
* getTrace() – 追踪机制
* getTraceAsString() – 格式化追踪的字符串

### 创建自定义异常处理程序

你可以创建自定义异常处理程序。使用以下函数来设置一个用户自定义的异常处理程序函数。

	string set_exception_handler ( callback $exception_handler ) 
这里未捕获的异常发生时调用名称被称为exception_handler函数。必须定义此函数之前调用set_exception_handler()。

例子:

	<?php
	function exception_handler($exception) {
	  echo "Uncaught exception: " , $exception->getMessage(), "\n";
	}
	
	set_exception_handler('exception_handler');
	
	throw new Exception('Uncaught Exception');
	
	echo "Not Executed\n";
	?>