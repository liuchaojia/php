
# 从MySQL数据库删除数据

可以通过PHP函数mysql_query执行SQL DELETE语句从MySQL表中删除数据。

下面是一个简单的例子从employee表删除记录。删除记录时使用条件条款应定位在任何表的某个记录。

下面的例子使用主键匹配员工表中的记录。

## 例子:

尝试以下的例子理解删除操作。您需要提供一个雇员ID从employee表删除一个雇员记录。

	<html>
	<head>
	<title>Delete a Record from MySQL Database</title>
	</head>
	<body>
	
	<?php
	if(isset($_POST['delete']))
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
	
	$sql = "DELETE employee ".
	       "WHERE emp_id = $emp_id" ;
	
	mysql_select_db('test_db');
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not delete data: ' . mysql_error());
	}
	echo "Deleted data successfully\n";
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
	<td width="100"> </td>
	<td> </td>
	</tr>
	<tr>
	<td width="100"> </td>
	<td>
	<input name="delete" type="submit" id="delete" value="Delete">
	</td>
	</tr>
	</table>
	</form>
	<?php
	}
	?>
	</body>
	</html>


