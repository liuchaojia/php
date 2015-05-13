
# PHP GET和POST方法

浏览器客户端有两种方法可以将信息发送到web服务器。　

* GET方法　
* POST方法 

浏览器发送信息之前,它的编码使用的一种是被称为URL编码的方案。在这个方案中, 使用名称/值与&不分离的方式。


    name1=value1&name2=value2&name3=value3

空格会被删除,取而代之的是+字符和其他任何非字母数字字符替换为十六进制值。信息编码后发送到服务器。

## $_GET 变量

GET方法发送编码用户信息添加到页面请求。页面和编码信息是由**?**字符分开。

    http://www.test.com/index.htm?name1=value1&name2=value2

* $_GET方法会在你的服务器日志输出一个长字符串, 出现在浏览器的位置:box框。
* GET方法仅局限于发送高达1024个字符。
* 如果你有密码或其他敏感信息，从不使用GET方法发送到服务器。
* 不能被用来发送二进制数据,如图像或word文档,到服务器。
* GET方法发送的数据可以使用QUERY_STRING环境变量访问。
* PHP提供了关联数组**$_GET**可以访问所有使用GET方法的发送信息。

试试下面的例子的源代码test.php脚本。

	<?php
	  if( $_GET["name"] || $_GET["age"] )
	  {
	     echo "Welcome ". $_GET['name']. "<br />";
	     echo "You are ". $_GET['age']. " years old.";
	     exit();
	  }
	?>
	<html>
	<body>
	  <form action="<?php $_PHP_SELF ?>" method="GET">
	  Name: <input type="text" name="name" />
	  Age: <input type="text" name="age" />
	  <input type="submit" />
	  </form>
	</body>
	</html>

## $_POST 变量

通过HTTP POST方法转移头信息。信息被编码可以描述为在GET方法的情况下,投入一个头称为QUERY_STRING。。

* POST方法没有任何要发送的数据大小限制。
* 可以使用POST方法发送ASCII和二进制数据。
* POST方法发送的数据通过HTTP头，所以安全依赖于HTTP协议。通过使用安全HTTP可以确保您的信息安全。
* PHP提供了$ _POST关联数组访问所有使用POST方法发送信息。

试试下面的例子在源代码test.php脚本中。

	<?php
	  if( $_POST["name"] || $_POST["age"] )
	  {
	     echo "Welcome ". $_POST['name']. "<br />";
	     echo "You are ". $_POST['age']. " years old.";
	     exit();
	  }
	?>
	<html>
	<body>
	  <form action="<?php $_PHP_SELF ?>" method="POST">
	
	  Name: <input type="text" name="name" />
	  Age: <input type="text" name="age" />
	
	  <input type="submit" />
	  </form>
	</body>
	</html>
     
## $_REQUEST 变量

PHP 的 $_REQUEST 变量包含了 $_GET, $_POST 以及 $_COOKIE 的内容。

PHP 的 $_REQUEST 变量可用来取得通过 GET 和 POST 方法发送的表单数据的结果。

试试下面的例子在源代码test.php脚本中。

	<?php
	  if( $_REQUEST["name"] || $_REQUEST["age"] )
	  {
	     echo "Welcome ". $_REQUEST['name']. "<br />";
	     echo "You are ". $_REQUEST['age']. " years old.";
	     exit();
	  }
	?>
	<html>
	<body>
	  <form action="<?php $_PHP_SELF ?>" method="POST">
	
	  Name: <input type="text" name="name" />
	  Age: <input type="text" name="age" />
	
	  <input type="submit" />
	  </form>
	</body>
	</html>

这里，$_PHP_SELF变量包含自我脚本的名称。

