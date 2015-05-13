# MySQL数据库连接

## 打开数据库连接：

PHP提供了mysql_connect（）函数打开一个数据库连接。此函数接受五个参数并返回一个MySQL成功连接标识符,;如果执行失败将返回FALSE。

语法：

	connection mysql_connect(server,user,passwd,new_link,client_flag);

<table class="table table-bordered"> 
<tr>
<th align="left" valign="top" width="20%">参数</th>
<th align="left" valign="top" width="80%">说明</th>
</tr>  
<tr><td>server</td><td>可选——运行数据库服务器上的主机名。如果没有指定,默认值是localhost:3306。
用户名	
密码	  
newlink</td></tr>
<tr><td>user</td><td>可选——访问数据库的用户名。如果没有指定,默认是用户拥有的服务器进程名称。</td></tr>
<tr><td>passwd</td><td> 可选——用户用密码访问数据库。如果没有指定,默认是空密码。</td></tr>
<tr><td>new_link</td><td>	可选。如果用同样的参数第二次调用 mysql_connect()，将不会建立新连接，而将返回已经打开的连接标识。参数 new_link 改变此行为并使 mysql_connect() 总是打开新的连接，甚至当 mysql_connect() 曾在前面被用同样的参数调用过。</td></tr>
<tr><td>client_flags</td><td>可选。client_flags 参数可以是以下常量的组合：



MYSQL_CLIENT_SSL - 使用 SSL 加密 
MYSQL_CLIENT_COMPRESS - 使用压缩协议
MYSQL_CLIENT_IGNORE_SPACE - 允许函数名后的间隔
MYSQL_CLIENT_INTERACTIVE - 允许关闭连接之前的交互超时非活动时间


</td></tr>
</table>

提示和注释：
您可以在服务器php.ini文件指定用户名和密码,而不是一次又一次的在你的每一个PHP脚本使用他们。检查php.ini文件配置。、

## 关闭数据库连接：

PHP提供了最简单的函数mysql_close关闭数据库连接。此函数接受mysql_connect函数返回的连接资源作为参数。成功它将返回TRUE;如果执行失败将返回FALSE。

语法：

	bool mysql_close ( resource $link_identifier );

如果没有指定一个资源,最后打开数据库被关闭。

### 例子：

下面的例子尝试打开和关闭数据库连接:

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'guest';
	$dbpass = 'guest123';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	echo 'Connected successfully';
	mysql_close($conn);
	?>
	
