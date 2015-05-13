
# 使用PHP删除MySQL数据库

## 删除一个数据库：

如果数据库不再需要那么它将可以被永远删除。您可以使用SQL命令传递给mysql_query执行删除一个数据库。

### 例子:

尝试以下例子来删除一个数据库。

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	$sql = 'DROP DATABASE test_db';
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not delete database db_test: ' . mysql_error());
	}
	echo "Database deleted successfully\n";
	mysql_close($conn);
	?>

警告: 对于删除一个数据库和表，它是非常危险的。所以删除任何表或数据库之前你应该确保你所做的一切是自愿的。

## 删除一个表：

它通过mysql_query函数再次的发出一个SQL命令来删除任何数据库和数据表。但使用这个命令时要非常小心,因为这样做你可以在你的桌面上删除一些重要的信息。

尝试以下示例删除一个表:

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	$sql = 'DROP TABLE employee';
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not delete table employee: ' . mysql_error());
	}
	echo "Table deleted successfully\n";
	mysql_close($conn);
	?>
