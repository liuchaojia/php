# 通过PHP使用分页

SQL SELECT语句查询出的结果可能达到几千的记录总是可能的。但在页面上显示所有结果显然不是一个好主意。所以我们可以把这个结果面按要求分为许多页。在多个页面中分页显示查询结果而不是把它们都放在一个页面中。

使用MySQL中的两个参数的限制条款有助于生成分页。

第一个参数偏移量和第二个参数有多少应该从数据库返回的记录。

下面是一个简单的例子对获取记录使用限制条款来生成分页。

## 例子:

尝试以下的例子每页显示10个记录。

	<html>
	<head>
	<title>Paging Using PHP</title>
	</head>
	<body>
	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$rec_limit = 10;
	
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	mysql_select_db('test_db');
	/* Get total number of records */
	$sql = "SELECT count(emp_id) FROM employee ";
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not get data: ' . mysql_error());
	}
	$row = mysql_fetch_array($retval, MYSQL_NUM );
	$rec_count = $row[0];
	
	if( isset($_GET{'page'} ) )
	{
	   $page = $_GET{'page'} + 1;
	   $offset = $rec_limit * $page ;
	}
	else
	{
	   $page = 0;
	   $offset = 0;
	}
	$left_rec = $rec_count - ($page * $rec_limit);
	
	$sql = "SELECT emp_id, emp_name, emp_salary ".
	       "FROM employee ".
	       "LIMIT $offset, $rec_limit";
	
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not get data: ' . mysql_error());
	}
	while($row = mysql_fetch_array($retval, MYSQL_ASSOC))
	{
	    echo "EMP ID :{$row['emp_id']}  <br> ".
	         "EMP NAME : {$row['emp_name']} <br> ".
	         "EMP SALARY : {$row['emp_salary']} <br> ".
	         "--------------------------------<br>";
	} 
	
	if( $page > 0 )
	{
	   $last = $page - 2;
	   echo "<a href=\"$_PHP_SELF?page=$last\">Last 10 Records</a> |";
	   echo "<a href=\"$_PHP_SELF?page=$page\">Next 10 Records</a>";
	}
	else if( $page == 0 )
	{
	   echo "<a href=\"$_PHP_SELF?page=$page\">Next 10 Records</a>";
	}
	else if( $left_rec < $rec_limit )
	{
	   $last = $page - 2;
	   echo "<a href=\"$_PHP_SELF?page=$last\">Last 10 Records</a>";
	}
	mysql_close($conn);
	?>
	
