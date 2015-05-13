# 网站概念PHP


本节演示了根据浏览器类型如何使用PHP可以提供动态页面内容，像随机生成的数字或用户输入。它还展示了客户端浏览器是可以被重定向的。

## 识别浏览器&平台


PHP创建一些有用的**环境变量**,可以在php运行phpinfo()函数看到PHP配置,用于设置php环境。

PHP环境变量集中的** HTTP_USER_AGENT** 是用来标识用户的浏览器和操作系统。

PHP提供了getenv()函数来访问所有的环境变量的值。

**HTTP_USER_AGENT** 环境变量中包含的信息适合于浏览器，可用于创建动态内容。下面的例子演示了如何识别客户浏览器和操作系统。

**注意:**函数preg_match()是在PHP正则表达式匹配函数
	    
	<html>
	<body>
	<?php
	   $viewer = getenv( "HTTP_USER_AGENT" );
	   $browser = "An unidentified browser";
	   if( preg_match( "/MSIE/i", "$viewer" ) )
	   {
	      $browser = "Internet Explorer";
	   }
	   else if(  preg_match( "/Netscape/i", "$viewer" ) )
	   {
	      $browser = "Netscape";
	   }
	   else if(  preg_match( "/Mozilla/i", "$viewer" ) )
	   {
	      $browser = "Mozilla";
	   }
	   $platform = "An unidentified OS!";
	   if( preg_match( "/Windows/i", "$viewer" ) )
	   {
	      $platform = "Windows!";
	   }
	   else if ( preg_match( "/Linux/i", "$viewer" ) )
	   {
	      $platform = "Linux!";
	   }
	   echo("You are using $browser on $platform");
	?>
	</body>
	</html>
   
    
    
    

这是在我的机器上产生后的结果。可能在不同的电脑依据所运行的环境会产生不同的结果。

    You are using Mozilla! on Windows!

## 随机显示图像

The PHP **rand()** function is used to generate a random number.i This function can generate numbers with-in a given range. The random number generator should be seeded to prevent a regular pattern of numbers being generated. This is achieved using the **srand()** function that specifiies the seed number as its argument.

Following example demonstrates how you can display different image each time out of four images:


PHP **rand()** 函数用于生成一个随机数。我这个函数可以会随机地在一个给定的范围内生成数字。随机数生成器打乱数字生成的规律。通过使用**srand()**函数,给它特定的种子数值作为它的参数。

以下示例演示了如何每次显示四个不同的图像的图片:

	<html>
	<body>
	<?php
	  srand( microtime() * 1000000 );
	  $num = rand( 1, 4 );
	   
	  switch( $num ) 
	  {
	  case 1: $image_file = "/home/images/alfa.jpg";
	          break;
	  case 2: $image_file = "/home/images/ferrari.jpg";
	          break;
	  case 3: $image_file = "/home/images/jaguar.jpg";
	          break;
	  case 4: $image_file = "/home/images/porsche.jpg";
	          break;
	  }
	  echo "Random Image : <img src=$image_file />";
	?>
	</body>
	</html>

使用HTML表单

最重要的事情是需要注意在处理HTML表单和PHP页面时,任何形式的表单元素都会提交到您的PHP脚本。试试下面的例子将在源代码test.php脚本运行。

	<?php
	  if( $_POST["name"] || $_POST["age"] )
	  {
	     echo "Welcome ". $_POST['name']. "<br />";
	     echo "You are ". $_POST['age']. " years old.";
	     exit();
	  }
	?>
	<html>
	<body>
	  <form action="<?php $_PHP_SELF ?>" method="POST">
	  Name: <input type="text" name="name" />
	  Age: <input type="text" name="age" />
	  <input type="submit" />
	  </form>
	</body>
	</html>

* PHP他默认变量$ _PHP_SELF用于输出PHP脚本名称，当你点击“提交”按钮时然后，PHP脚本将被调用，将会产生以下结果: 
* method=“POST”用于用户发送数据到服务器脚本。在PHP中有两个方法可以上传数据到服务器脚本，GET和POST将在以后的章节讨论。
    
## 浏览器重定向
         
PHP**header()**函数提供原始HTTP headers到浏览器,可用于重定向到另一个位置。重定向脚本应该在页面的顶端,以防止加载页面的其他部分。

**Location:**用来指定目标位置:**header()**函数使用url作为参数。在调用该函数之后使用**exit()** 函数可以阻止其他代码的解析

下面的例子演示了如何将浏览器请求重定向到另一个web页面。试试这个例子test.php源代码的脚本。
	<?php
	  if( $_POST["location"] )
	  {
	     $location = $_POST["location"];
	     header( "Location:$location" );
	     exit();
	  }
	?>
	<html>
	<body>
	   <p>Choose a site to visit :</p>
	   <form action="<?php $_PHP_SELF ?>" method="POST">
	   <select name="location">
	      <option value="http://w3c.org">
	            World Wise Web Consortium
	      </option>
	      <option value="http://www.google.com">
	            Google Search Page
	      </option>
	   </select>
	   <input type="submit" />
	   </form>
	</body>
	</html>

## 显示“文件下载”对话框

某个时候显示“文件下载”对话框是想要的功能,你想给使用选项当用户点击一个链接,它就会弹出一个“文件下载”显示框给用户而不是显示实际内容。通过HTTP头协议这是非常容易的。

HTTP头协议将不同于实际的协议,我们发送的 **Content-Type**为**text/htmlnn**。在这种情况下,将**application/octet-stream**和实际文件名称将连接到一起。

例如,如果你想要从一个给定的文件名文件下载链接，那么它的语法将如下。

    #!/usr/bin/perl
	# HTTP Header
	print "Content-Type:application/octet-stream; name=\"FileName\"\r\n";
	print "Content-Disposition: attachment; filename=\"FileName\"\r\n\n";
	
	# Actual File Content
	open( FILE, "<FileName" );
	while(read(FILE, $buffer, 100) )
	{
	   print("$buffer");
	}

