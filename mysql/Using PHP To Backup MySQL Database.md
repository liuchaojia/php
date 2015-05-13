# 使用PHP备份MySQL数据库

It is always good practice to take a regular backup of your database. There are three ways you can use to take backup of your MySQL database.
•	Using SQL Command through PHP.
•	Using MySQL binary mysqldump through PHP.
•	Using phpMyAdmin user interface.
定期备份你的数据库总是一种好的做法。有三种方法可以使用备份你的MySQL数据库。

* 通过PHP使用SQL命令。
* 使用MySQL二进制通过PHP mysqldump。
* 使用phpMyAdmin的用户界面。

## 通过PHP使用SQL命令

可以执行SQL SELECT命令完成任何表的备份。把一个完整的数据库存储您需要为单独的表编写单独的查询。每个表将存储到单独的文本文件中。
### 例子

试试以下的例子使用SELECT INTO OUTFILE查询用于创建表的备份:

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	$table_name = "employee";
	$backup_file  = "/tmp/employee.sql";
	$sql = "SELECT * INTO OUTFILE '$backup_file' FROM $table_name";
	
	mysql_select_db('test_db');
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not take data backup: ' . mysql_error());
	}
	echo "Backedup  data successfully\n";
	mysql_close($conn);
	?>

可能存在实例,当你需要恢复数据备份的前一段时间。恢复备份你只需要运行数据加载INFILE查询如下:

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	$table_name = "employee";
	$backup_file  = "/tmp/employee.sql";
	$sql = "LOAD DATA INFILE '$backup_file' INTO TABLE $table_name";
	
	mysql_select_db('test_db');
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not load data : ' . mysql_error());
	}
	echo "Loaded  data successfully\n";
	mysql_close($conn);
	?>

## 使用MySQL通过PHP二进制mysqldump

MySQL提供一个实用程序,mysqldump执行数据库备份。使用这种二进制您可以在一个命令得到完整的数据库转储。

### 例子：

下面的例子尝试把你完整的数据库转储:

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	
	$backup_file = $dbname . date("Y-m-d-H-i-s") . '.gz';
	$command = "mysqldump --opt -h $dbhost -u $dbuser -p $dbpass ".
	           "test_db | gzip > $backup_file";
	
	system($command);
	?>
## 使用phpMyAdmin用户界面:

如果你有phpMyAdmin用户界面可用,它很容易为你备份你的数据库。

备份您的MySQL数据库使用phpMyAdmin点击phpMyAdmin主页上的“出口”链接。您希望备份数据库,检查适当的SQL选项和输入备份文件的名称。
