
# 更新数据到MySQL数据库中

数据可以通过使用PHP函数mysql_query（）执行SQL UPDATE语句将数据更新到MySQL表中。

下面是一个简单的例子更新记录到员工表中。更新记录应使用条件条款定位在任何表中的位置。

下面的例子使用主键匹配员工表中的记录。
## 例子：

试试以下的例子可以使您理解更新操作。你需要提供一个ID来更新雇员的薪水。

	<html>
	<head>
	<title>Update a Record in MySQL Database</title>
	</head>
	<body>
	
	<?php
	if(isset($_POST['update']))
	{
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	
	$emp_id = $_POST['emp_id'];
	$emp_salary = $_POST['emp_salary'];
	
	$sql = "UPDATE employee ".
	       "SET emp_salary = $emp_salary ".
	       "WHERE emp_id = $emp_id" ;
	
	mysql_select_db('test_db');
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not update data: ' . mysql_error());
	}
	echo "Updated data successfully\n";
	mysql_close($conn);
	}
	else
	{
	?>
	<form method="post" action="<?php $_PHP_SELF ?>">
	<table width="400" border="0" cellspacing="1" cellpadding="2">
	<tr>
	<td width="100">Employee ID</td>
	<td><input name="emp_id" type="text" id="emp_id"></td>
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
	<input name="update" type="submit" id="update" value="Update">
	</td>
	</tr>
	</table>
	</form>
	<?php
	}
	?>
	</body>
	</html>
