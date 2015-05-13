# 用PHP创建mysql数据库

## 创建一个数据库：

创建和删除数据库你应该有管理特权。它很容易创建一个新的MySQL数据库。PHP使用mysql_query函数创建一个MySQL数据库。这个函数接受两个参数执行成功并返回TRUE;;如果执行失败将返回FALSE。

### 语法：

	bool mysql_query( sql, connection );


<table class="table table-bordered">
<tr>
<th align="left" valign="top" width="20%">参数
</th>
<th align="left" valign="top" width="80%">	说明</th>
</tr>
<tr><td>sql</td><td>必填-----用 SQL查询语句创建一个数据库</td></tr>
<tr><td>connection</td><td>可选的,如果没有指定,那么最后只连接到mysql_connect将被使用。</td></tr>
</table>

### 例子：
Try out following example to create a database:
试运行以下例子创建数据库：

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	echo 'Connected successfully';
	$sql = 'CREATE Database test_db';
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not create database: ' . mysql_error());
	}
	echo "Database test_db created successfully\n";
	mysql_close($conn);
	?>

## 选择一个数据库:
一旦你打开一个连接到一个数据库服务器,那么它将需要选择一个特定的数据库相关联的所有表的地方。
这是必需的,因为可能有多个数据库驻留在一个单独的服务器上,你可以使用一个数据库。
PHP提供了函数mysql_select_db选择一个数据库。成功它将返回TRUE;如果执行失败将返回FALSE。

### 语法：

	bool mysql_select_db( db_name, connection );

<table class="table table-bordered"> 
<tr>
<th align="left" valign="top" width="20%">参数
</th>
<th align="left" valign="top" width="80%">说明</th>
</tr>  
<tr><td>db_name</td><td>必填-----选择数据库名称</td></tr>
<tr><td>connection</td><td>可选的,如果没有指定,那么最后只连接到mysql_connect将被使用。</td></tr>
</table>

### 例子：

这里的示例向您展示如何选择一个数据库

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
	mysql_select_db( 'test_db' );
	mysql_close($conn);
	?>

## 创建数据库表:

创建新的数据库中的表你需要做同样的事情就像创建数据库。首先使用SQL查询创建表然后使用mysql_query()函数执行查询。

例如:尝试以下示例创建一个表:

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	echo 'Connected successfully';
	$sql = 'CREATE TABLE employee( '.
	       'emp_id INT NOT NULL AUTO_INCREMENT, '.
	       'emp_name VARCHAR(20) NOT NULL, '.
	       'emp_address  VARCHAR(20) NOT NULL, '.
	       'emp_salary   INT NOT NULL, '.
	       'join_date    timestamp(14) NOT NULL, '.
	       'primary key ( emp_id ))';
	
	mysql_select_db('test_db');
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not create table: ' . mysql_error());
	}
	echo "Table employee created successfully\n";
	mysql_close($conn);
	?>

在一定情况下,您需要创建许多表首先最好先创建一个文本文件,把所有的SQL命令写到文本文件中,然后执行这些命令将该文件导入到mysq数据库中。

考虑以下内容sql_query.txt文件

	CREATE TABLE employee(
	     emp_id INT NOT NULL AUTO_INCREMENT,
	     emp_name VARCHAR(20) NOT NULL,
	     emp_address  VARCHAR(20) NOT NULL,
	     emp_salary   INT NOT NULL,
	     join_date    timestamp(14) NOT NULL,
	     primary key ( emp_id ));
	
	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	$query_file = 'sql_query.txt';
	
	$fp    = fopen($query_file, 'r');
	$sql = fread($fp, filesize($query_file));
	fclose($fp); 
	
	mysql_select_db('test_db');
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not create table: ' . mysql_error());
	}
	echo "Table employee created successfully\n";
	mysql_close($conn);
	?>