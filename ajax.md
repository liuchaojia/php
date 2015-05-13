# PHP 和 AJAX学习

## AJAX是什么?

* AJAX代表异步JavaScript和XML。AJAX是一种新技术在XML、HTML、CSS和Java帮助下来创建更好、更快、交互式web应用程序的脚本语言。
* 传统web应用程序从服务器传送信息和使用同步请求。这意味着你填写表格,点击提交,获得定向到一个新的从服务器获取信息页面。
* 使用AJAX提交按钮被按下时,JavaScript将发送一个请求到服务器,解释结果和更新当前屏幕。在纯粹意义上,用户甚至不会知道什么时候把请求传送到服务器上。

对于AJAX学习,请参阅AJAX教程
## PHP and AJAX 例子:

明确说明使用Ajax和PHP是非常容易从数据库中获取信息,我们要在“ajax.html”建立动态MySQL查询和显示结果。但在我们继续进行工作之前,让ajax做下工作。可以使用以下命令创建一个表。

注释：我们确保您有足够的权限来执行MySQL操作

	CREATE TABLE `ajax_example` (
	  `name` varchar(50) NOT NULL,
	  `age` int(11) NOT NULL,
	  `sex` varchar(1) NOT NULL,
	  `wpm` int(11) NOT NULL,
	  PRIMARY KEY  (`name`)
	) 
现在使用以下 SQL语句将以下数据转储到此表

	INSERT INTO `ajax_example` VALUES ('Jerry', 120, 'm', 20);
	INSERT INTO `ajax_example` VALUES ('Regis', 75, 'm', 44);
	INSERT INTO `ajax_example` VALUES ('Frank', 45, 'm', 87);
	INSERT INTO `ajax_example` VALUES ('Jill', 22, 'f', 72);
	INSERT INTO `ajax_example` VALUES ('Tracy', 27, 'f', 0);
	INSERT INTO `ajax_example` VALUES ('Julie', 35, 'f', 90);

## 客户端HTML文件

现在可以让我们的客户端HTML文件创建ajax。如下是html和它的代码

	<html>
	<body>
	<script language="javascript" type="text/javascript">
	<!-- 
	//Browser Support Code
	function ajaxFunction(){
	 var ajaxRequest;  // The variable that makes Ajax possible!
		
	 try{
	   // Opera 8.0+, Firefox, Safari
	   ajaxRequest = new XMLHttpRequest();
	 }catch (e){
	   // Internet Explorer Browsers
	   try{
	      ajaxRequest = new ActiveXObject("Msxml2.XMLHTTP");
	   }catch (e) {
	      try{
	         ajaxRequest = new ActiveXObject("Microsoft.XMLHTTP");
	      }catch (e){
	         // Something went wrong
	         alert("Your browser broke!");
	         return false;
	      }
	   }
	 }
	 // Create a function that will receive data 
	 // sent from the server and will update
	 // div section in the same page.
	 ajaxRequest.onreadystatechange = function(){
	   if(ajaxRequest.readyState == 4){
	      var ajaxDisplay = document.getElementById('ajaxDiv');
	      ajaxDisplay.innerHTML = ajaxRequest.responseText;
	   }
	 }
	 // Now get the value from user and pass it to
	 // server script.
	 var age = document.getElementById('age').value;
	 var wpm = document.getElementById('wpm').value;
	 var sex = document.getElementById('sex').value;
	 var queryString = "?age=" + age ;
	 queryString +=  "&wpm=" + wpm + "&sex=" + sex;
	 ajaxRequest.open("GET", "ajax-example.php" + 
	                              queryString, true);
	 ajaxRequest.send(null); 
	}
	//-->
	</script>
	<form name='myForm'>
	Max Age: <input type='text' id='age' /> <br />
	Max WPM: <input type='text' id='wpm' />
	<br />
	Sex: <select id='sex'>
	<option value="m">m</option>
	<option value="f">f</option>
	</select>
	<input type='button' onclick='ajaxFunction()' 
	                              value='Query MySQL'/>
	</form>
	<div id='ajaxDiv'>Your result will display here</div>
	</body>
	</html>

注意:查询中传递变量的方式必须遵循HTTP标准和形式

	URL?variable1=value1;&variable2=value2;

现在上面的代码将会产生如下一个表格

注意:这是虚拟屏幕,不能运行

Max Age:   

Max WPM:  

Sex: 

运行结果将会展现在这里


## 服务器端PHP文件

现在你的客户端脚本已经准备好了。现在我们必须编写服务器端脚本将获取的年龄, 每分钟字数和性别从数据库取出并将其发送回客户端。把以下代码为“ajax-example.php”文件

	<?php
	$dbhost = "localhost";
	$dbuser = "dbusername";
	$dbpass = "dbpassword";
	$dbname = "dbname";
		//Connect to MySQL Server
	mysql_connect($dbhost, $dbuser, $dbpass);
		//Select Database
	mysql_select_db($dbname) or die(mysql_error());
		// Retrieve data from Query String
	$age = $_GET['age'];
	$sex = $_GET['sex'];
	$wpm = $_GET['wpm'];
		// Escape User Input to help prevent SQL Injection
	$age = mysql_real_escape_string($age);
	$sex = mysql_real_escape_string($sex);
	$wpm = mysql_real_escape_string($wpm);
		//build query
	$query = "SELECT * FROM ajax_example WHERE sex = '$sex'";
	if(is_numeric($age))
		$query .= " AND age <= $age";
	if(is_numeric($wpm))
		$query .= " AND wpm <= $wpm";
		//Execute query
	$qry_result = mysql_query($query) or die(mysql_error());
	
		//Build Result String
	$display_string = "<table>";
	$display_string .= "<tr>";
	$display_string .= "<th>Name</th>";
	$display_string .= "<th>Age</th>";
	$display_string .= "<th>Sex</th>";
	$display_string .= "<th>WPM</th>";
	$display_string .= "</tr>";
	
	// Insert a new row in the table for each person returned
	while($row = mysql_fetch_array($qry_result)){
		$display_string .= "<tr>";
		$display_string .= "<td>$row[name]</td>";
		$display_string .= "<td>$row[age]</td>";
		$display_string .= "<td>$row[sex]</td>";
		$display_string .= "<td>$row[wpm]</td>";
		$display_string .= "</tr>";
		
	}
	echo "Query: " . $query . "<br />";
	$display_string .= "</table>";
	echo $display_string;
	?>

现在试着输入一个有效的值“Max Age”或任何其他输入框,然后点击查询按钮

Max Age:   

Max WPM:  

Sex: 

你的查询结果将会在这里展示

如果你已经充分地理解了这节课,那么你会知道如何使用MySQL,PHP,HTML和Javascript串联编写Ajax应用程序

