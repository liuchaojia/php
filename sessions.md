

# PHP Sessions

另一种方法是使用PHP会话，使数据可访问整个网站的各个页面。

一个会话在服务器上的一个临时目录中创建了一个文件用来存储会话变量及其值。这些数据将可以在网站的所有页面中被访问到。

临时文件的位置是在php.ini文件中称为session.save_path中设置的。确保使用任何会话变量之前确定你已经设置这条路径。

当一个会话启动需要做以下事情: 　
　

* PHP特定会话首先会创建一个惟一的标识符，这个标识符是一个随机的32伪十六进制数字的字符串3c7foj34c3jj973hjkop2fc937e3443。　　　　
* 一个cookie调用PHPSESSID自动发送到用户的电脑存储独特的会话识别的字符串。
* 在指定服务器上会自动创建临时目录里的文件，这个文件存储名称前缀为sess_ 的 sess_3c7foj34c3jj973hjkop2fc937e3443的唯一标识符。

当PHP脚本要检索一个会话变量中的值,PHP会自动获得独特的会话标识符的字符串PHPSESSID cookie,然后在其临时目录的文件中可以通过比较两个值进行验证。

当用户关闭了浏览器或离开浏览器后会话结束, 一般在预定时间后30分钟，服务器将终止该会话。

## 开始一个PHP会话:

通过调用session_start()函数一个PHP会话很容易开始。这个函数首先检查如果已经开始一个会话或者没有开始会话那么开启一个会话。建议把调用session_start()函数放在页面的头部。

会话变量存储在名为$ _SESSION[]的关联数组中。这些变量可以在一个会话的生命周期内被访问。
下面的例子开始一个会话然后注册一个变量counter,会话期间每次访问页面可以加载这个变量。

把这段代码放在test.php文件中然后加载这个文件多次查看结果:

通过调用session_start()函数一个PHP会话很容易开始。这个函数首先检查如果已经开始一个会话或者没有开始会话那么开启一个会话。建议把调用session_start()函数放在页面的头部。

会话变量存储在名为$ _SESSION[]的关联数组中。这些变量可以在一个会话的生命周期内被访问。
下面的例子开始一个会话然后注册一个变量counter,会话期间每次访问页面可以加载这个变量。

把这段代码放在test.php文件中然后加载这个文件多次查看结果:

	<?php
	   session_start();
	   if( isset( $_SESSION['counter'] ) )
	   {
	      $_SESSION['counter'] += 1;
	   }
	   else
	   {
	      $_SESSION['counter'] = 1;
	   }
	   $msg = "You have visited this page ".  $_SESSION['counter'];
	   $msg .= "in this session.";
	?>
	<html>
	<head>
	<title>Setting up a PHP session</title>
	</head>
	<body>
	<?php  echo ( $msg ); ?>
	</body>
	</html>

## 销毁一个PHP会话:

使用session_destroy()函数可以使一个PHP会话被销毁。这个函数不需要任何参数,单个调用就可以摧毁所有会话变量。如果你想要摧毁一个会话变量,那么你可以使用unset()函数来删除一个会话变量。

这是示例删除一个变量:
	
	<?php
	   unset($_SESSION['counter']);
	?>

这是函数将会摧毁所有的会话变量:

	<?php
	   session_destroy();
	?>

## 打开自动会话:

如果你在PHP.INI文件中设置session.auto_start变量为1,当用户访问你的网站时你不需要调用start_session()函数来启动一个会话。

## Sessions是基于Cookie的
或许有这么一种情况当用户不允许在他们的机器中存储cookies时。所以还有另一个方法将sessionID发送到浏览器。

或者,您可以使用常数SID如果会话开始时被定义。如果客户端没有发送一个合适的会话cookie,它的形式是session_name = session_id。不然,它会填充到一个空字符串。因此,你可以无条件地嵌入到urls。

下面的例子演示了如何注册一个变量,以及如何使用SID正确的链接到另一个页面。

	<?php
	   session_start();
	
	   if (isset($_SESSION['counter'])) {
	      $_SESSION['counter'] = 1;
	   } else {
	      $_SESSION['counter']++;
	   }
	?>
	   $msg = "You have visited this page ".  $_SESSION['counter'];
	   $msg .= "in this session.";
	   echo ( $msg );
	<p>
	To continue  click following link <br />
	<a  href="nextpage.php?<?php echo htmlspecialchars(SID); >">
	</p>

当打印SID时函数htmlspecialchars ()为了防止XSS攻击。