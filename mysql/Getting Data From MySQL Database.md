
# 使用PHP从数据库取数据,

可以通过PHP函数mysql_query执行SQL SELECT语句从MySQL表中获取的数据。你有几个选项可以从MySQL获取数据。

最常用的方法是使用函数mysql_fetch_array()。这个函数返回的是作为一个关联数组结果集和一个索引数组结果集,或两者兼而有之。这个函数如果没有更多的行将返回FALSE。

下面是一个简单的例子从employee表获取记录。
## 例子

尝试以下例子来显示employee表的所有记录。

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	$sql = 'SELECT emp_id, emp_name, emp_salary FROM employee';
	
	mysql_select_db('test_db');
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
	echo "Fetched data successfully\n";
	mysql_close($conn);
	?>

这些结果集中的内容被分配给变量$row并且结果集中的值被打印出来。

注意:永远记住当你想插入数组的值到一个字符串要使用花括号。

在上面例子中常量MYSQL_ASSOC作为mysql_fetch_array（）函数的第二个参数,以便它返回作为一个关联数组的结果集。通过使用一个关联数组的名字可以访问字段,而不是使用索引。

PHP提供了另一个函数称为mysql_fetch_assoc()也返回作为一个关联数组的结果集。
## 例子：

尝试以下例子使用mysql_fetch_assoc()函数从employee表来显示所有记录。

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	$sql = 'SELECT emp_id, emp_name, emp_salary FROM employee';
	
	mysql_select_db('test_db');
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not get data: ' . mysql_error());
	}
	while($row = mysql_fetch_assoc($retval))
	{
	    echo "EMP ID :{$row['emp_id']}  <br> ".
	         "EMP NAME : {$row['emp_name']} <br> ".
	         "EMP SALARY : {$row['emp_salary']} <br> ".
	         "--------------------------------<br>";
	} 
	echo "Fetched data successfully\n";
	mysql_close($conn);
	?>

您还可以使用常量MYSQL_NUM,作为mysql_fetch_array()函数的第二个参数。这将导致该函数返回一个索引数组。
## 例子：

尝试以下例子使用常量MYSQL_NUM从employee表中取数据来显示所有记录。

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	$sql = 'SELECT emp_id, emp_name, emp_salary FROM employee';
	
	mysql_select_db('test_db');
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not get data: ' . mysql_error());
	}
	while($row = mysql_fetch_array($retval, MYSQL_NUM))
	{
	    echo "EMP ID :{$row[0]}  <br> ".
	         "EMP NAME : {$row[1]} <br> ".
	         "EMP SALARY : {$row[2]} <br> ".
	         "--------------------------------<br>";
	}
	echo "Fetched data successfully\n";
	mysql_close($conn);
	?>
 
上述三个例子将产生相同的结果。

释放内存:一个好的习惯是释放游标记忆在每个SELECT语句结束时。这可以通过使用PHP函数mysql_free_result()函数来进行操作。下面的例子显示如何使用。

## 例子:尝试以下的例子

	<?php
	$dbhost = 'localhost:3036';
	$dbuser = 'root';
	$dbpass = 'rootpassword';
	$conn = mysql_connect($dbhost, $dbuser, $dbpass);
	if(! $conn )
	{
	  die('Could not connect: ' . mysql_error());
	}
	$sql = 'SELECT emp_id, emp_name, emp_salary FROM employee';
	
	mysql_select_db('test_db');
	$retval = mysql_query( $sql, $conn );
	if(! $retval )
	{
	  die('Could not get data: ' . mysql_error());
	}
	while($row = mysql_fetch_array($retval, MYSQL_NUM))
	{
	    echo "EMP ID :{$row[0]}  <br> ".
	         "EMP NAME : {$row[1]} <br> ".
	         "EMP SALARY : {$row[2]} <br> ".
	         "--------------------------------<br>";
	}
	mysql_free_result($retval);
	echo "Fetched data successfully\n";
	mysql_close($conn);
	?>

获取数据时您可以编写复杂的SQL。过程仍将与上面提到的相同。

