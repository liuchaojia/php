# PHP Cookies

Cookies是文本文件存储在计算机客户端, 目的是用来跟踪用户的。PHP完全地支持HTTP cookie。

有三个步骤参与识别返回用户: 　
　　　

* 服务器脚本向浏览器发送的cookie。例如姓名、年龄、身份证号码等。　　　　
* 浏览器将这个信息存储在本地机器上,以供将来使用。　　　　
* 下次当浏览器向web服务器发送任何请求然后浏览器将这些cookie信息发送给服务器,服务器使用这些信息来识别用户。

本章将教你如何设置cookie,如何访问它们,以及如何删除它们。

## 一个cookie的剖析:
cookie通常设置在一个HTTP头信息里面(尽管JavaScript浏览器也可以直接设置cookie)。一个PHP脚本,设置cookie发送头信息看起来是这样的:

	HTTP/1.1 200 OK
	Date: Fri, 04 Feb 2000 21:03:38 GMT
	Server: Apache/1.3.9 (UNIX) PHP/4.0b3
	Set-Cookie: name=xyz; expires=Friday, 04-Feb-07 22:03:38 GMT; 
	                 path=/; domain=tutorialspoint.com
	Connection: close
	Content-Type: text/html

如您所见,Set-Cookie头包含一个名称值对,格林尼治时间日期、路径和一个域名。名称和值将由URL编码。到期字段是“forget”的指令到浏览器cookie在给定的时间和日期。

如果浏览器配置存储cookies,然后它会保存这个信息直到日期过期。如果用户点浏览器在任何页面并且和cookie的路径和域名相匹配,那么它将重新发送cookie到服务器。浏览器的标题看起来是这样的:

	GET / HTTP/1.0
	Connection: Keep-Alive
	User-Agent: Mozilla/4.6 (X11; I; Linux 2.2.6-15apmac ppc)
	Host: zink.demon.co.uk:1126
	Accept: image/gif, */*
	Accept-Encoding: gzip
	Accept-Language: en
	Accept-Charset: iso-8859-1,*,utf-8
	Cookie: name=xyz

一个PHP脚本将访问环境变量的$_COOKIE或持有所有cookie的名称和值d的$HTTP_COOKIE_VARS[]。以上cookie可以使用$HTTP_COOKIE_VARS["name"]。

## 在PHP中设置cookie:

PHP提供了setcookie()函数来设置cookie。该函数需要高达六个参数,应该在< html >标记之前调用。每个cookie分别必须调用此函数。
	
	setcookie(name, value, expire, path, domain, security);
这是详细的参数: 　
　　　

* Name——这设置cookie的名称和存储在一个名为HTTP_COOKIE_VARS的环境变量。这个变量是在访问使用cookie。　　　　
* Value——指定变量的值,是你实际想要存储的内容。　　　　
* Expiry——这指定一个未来的时间以秒为单位就是从1970年1月1日格林尼治时间之后。这个时间之后* * Cookie将无法访问。如果cookie里面没有设置这个参数，Web浏览器关闭时将自动过期。　　　　
* Path——指定目录中cookie是有效的。一个正斜杠字符允许所有目录的cookie有效。　　　　
* Domain——这可以在非常大的领域里用来指定域名在并且必须包含至少两个有效的时期。创建Cookie都是唯一有效的主机和域名。
* Security——这可以设置为1可以指定发送的cookie只能使用HTTPS安全传输,否则设置为0意味着可以定期发送的HTTP cookie。

以下示例将创建两个cookies name和 age,这些cookie将一小时后过期。

	<?php
	   setcookie("name", "John Watkin", time()+3600, "/","", 0);
	   setcookie("age", "36", time()+3600, "/", "",  0);
	?>
	<html>
	<head>
	<title>Setting Cookies with PHP</title>
	</head>
	<body>
	<?php echo "Set Cookies"?>
	</body>
	</html>

## 使用PHP访问Cookies 
PHP提供了许多方法来访问cookie。最简单的方法是使用$_COOKIE或$HTTP_COOKIE_VARS变量。

以下示例将访问所有的上面的例子中的cookie。

	<html>
	<head>
	<title>Accessing Cookies with PHP</title>
	</head>
	<body>
	<?php
	echo $_COOKIE["name"]. "<br />";
	/* is equivalent to */
	echo $HTTP_COOKIE_VARS["name"]. "<br />";
	
	echo $_COOKIE["age"] . "<br />";
	/* is equivalent to */
	echo $HTTP_COOKIE_VARS["name"] . "<br />";
	?>
	</body>
	</html>
您可以使用isset()函数检查是否设置cookie。

	<html>
	<head>
	<title>Accessing Cookies with PHP</title>
	</head>
	<body>
	<?php
	  if( isset($_COOKIE["name"]))
	    echo "Welcome " . $_COOKIE["name"] . "<br />";
	  else
	    echo "Sorry... Not recognized" . "<br />";
	?>
	</body>
	</html>
## 使用PHP删除Cookie
正式地删除一个cookie应该使用setcookie()函数的name 参数但是这样工作总是不好，然而不应该有依赖。

最安全的方法是设置cookie的日期已经过期:

	<?php
	  setcookie( "name", "", time()- 60, "/","", 0);
	  setcookie( "age", "", time()- 60, "/","", 0);
	?>
	<html>
	<head>
	<title>Deleting Cookies with PHP</title>
	</head>
	<body>
	<?php echo "Deleted Cookies" ?>
	</body>
	</html>