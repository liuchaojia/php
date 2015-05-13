
# 插入数据到MySQL数据库

 
数据可以通过mysql_query PHP函数执行SQL INSERT语句输入到MySQL表中。下面一个简单的例子将记录插入到employee表。
## 例子：

尝试以下例子将记录插入到employee表。

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	$sql = 'INSERT INTO employee '.
	       '(emp_name,emp_address, emp_salary, join_date) '.
	       'VALUES ( "guest", "XYZ", 2000, NOW() )';
	
	mysql_select_db('test_db');
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not enter data: ' . mysql_error());
	}
	echo "Entered data successfully\n";
	mysql_close($conn);
	?>

在真实的应用程序中,所有的值都将使用HTML表单进行提交,然后这些值将使用PHP脚本被捕获,最后将他们插入到MySQL数据表。

在当数据插入之前它的最佳实践是使用功能get_magic_quotes_gpc()来查看当前魔法配置引号函数是否已经设置。如果这个函数返回false,那么请使用函数addslashes()在引号之前添加斜杠。

## 例子:
尝试将这段代码放入add_employee.php文件中,这将需要使用HTML表单进行输入,然后它将创建记录到数据库中。

	<html>
	<head>
	<title>Add New Record in MySQL Database</title>
	</head>
	<body>
	<?php
	if(isset($_POST['add']))
	{
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	
	if(! get_magic_quotes_gpc() )
	{
	   $emp_name = addslashes ($_POST['emp_name']);
	   $emp_address = addslashes ($_POST['emp_address']);
	}
	else
	{
	   $emp_name = $_POST['emp_name'];
	   $emp_address = $_POST['emp_address'];
	}
	$emp_salary = $_POST['emp_salary'];
	
	$sql = "INSERT INTO employee ".
	       "(emp_name,emp_address, emp_salary, join_date) ".
	       "VALUES('$emp_name','$emp_address',$emp_salary, NOW())";
	mysql_select_db('test_db');
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not enter data: ' . mysql_error());
	}
	echo "Entered data successfully\n";
	mysql_close($conn);
	}
	else
	{
	?>
	<form method="post" action="<?php $_PHP_SELF ?>">
	<table width="400" border="0" cellspacing="1" cellpadding="2">
	<tr>
	<td width="100">Employee Name</td>
	<td><input name="emp_name" type="text" id="emp_name"></td>
	</tr>
	<tr>
	<td width="100">Employee Address</td>
	<td><input name="emp_address" type="text" id="emp_address"></td>
	</tr>
	<tr>
	<td width="100">Employee Salary</td>
	<td><input name="emp_salary" type="text" id="emp_salary"></td>
	</tr>
	<tr>
	<td width="100"> </td>
	<td> </td>
	</tr>
	<tr>
	<td width="100"> </td>
	<td>
	<input name="add" type="submit" id="add" value="Add Employee">
	</td>
	</tr>
	</table>
	</form>
	<?php
	}
	?>
	</body>
	</html>
	
