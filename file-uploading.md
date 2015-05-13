# PHP 文件上传

PHP脚本允许用户使用HTML格式上传文件到服务器上。最初的文件被上传到一个临时目录中, 随后PHP脚本将其转移到最终目录中。

在phpinfo.php页面中信息描述用于文件上传的临时目录为upload_tmp_dir, 并且允许最大上传文件为upload_max_filesize。这些参数被设置在PHP配置文件PHP.ini中

上传文件步骤如下:　
　

* 用户打开页面, 其中包含HTML文本文件表单, 浏览按钮和提交按钮。　　　　
* 用户单击浏览按钮并从本地电脑上选择文件上传。　
* 选中文件的完整路径出现在文本框中, 然后单击提交按钮。　　　　
* 所选文件被发送到服务器上的临时目录中。　　　　
* 定形的PHP脚本处理程序检查已经到达文件, 然后将其复制到目标目录中。
* PHP脚本确认上传成功。

通常, 在临时和最终的位置中,写入文件设置权限为允许是很有必要的。如果被设置为只读那么过程将会失败
一个上传文件可以是一个文本文件或图像文件或任何其他文档。
## 创建上传表单:
下面HTML代码创建了一个上传表单。这种表单属性设置为post, enctype属性设置为multipart/from-data

创建上传表单:
下面HTML代码创建了一个上传表单。这种表单属性设置为post, enctype属性设置为multipart/from-data
	
	<html>
	<head>
	<title>File Uploading Form</title>
	</head>
	<body>
	<h3>File Upload:</h3>
	Select a file to upload: <br />
	<form action="/php/file_uploader.php" method="post"
	                        enctype="multipart/form-data">
	<input type="file" name="file" size="50" />
	<br />
	<input type="submit" value="Upload File" />
	</form>
	</body>
	</html>

显示效果如下：
	
	File Upload:
	Select a file to upload: 
	
	
	
	
	NOTE: This is just dummy form and would not work.
	
	
	 
## 创建一个上传脚本:

有一个全球PHP变量名为$ _file。这个变量是二维数组, 保留了所有上传文件的相关信息。因此,如果分配给在上传表单输入值的名称File,那么PHP将创建5个变量:


* **$_FILES['file']['tmp_name']-**——上传文件在web服务器上的临时目录。　　　　
* **$_FILES['file']['name']**——上传文件的真实名称。　　　　
* **$_FILES['file']['size']**——上传文件的大小(以字节。　　　　
* **$_FILES['file']['type']**——上传文件的MIME类型。　　　　
* **$_FILES['file']['error']**——与此文件上传相关的错误代码。


下面例子中脚本试图复制一个在前一节中列出HTML表单上传的文件到/var/www/html目录中，这是PHP服务器文档的根目录，在完成后它会显示所有文件的细节。请注意,如果您要显示上传文件不要使用二进制文件如图片或Word文档。

uploader.php脚本将确保文件的上传。

	<?php
	if( $_FILES['file']['name'] != "" )
	{
	   copy( $_FILES['file']['name'], "/var/www/html" ) or 
	           die( "Could not copy file!");
	}
	else
	{
	    die("No file specified!");
	}
	?>
	<html>
	<head>
	<title>Uploading Complete</title>
	</head>
	<body>
	<h2>Uploaded File Info:</h2>
	<ul>
	<li>Sent file: <?php echo $_FILES['file']['name'];  ?>
	<li>File size: <?php echo $_FILES['file']['size'];  ?> bytes
	<li>File type: <?php echo $_FILES['file']['type'];  ?>
	</ul>
	</body>
	</html>
当你将使用表单上传和脚本上传文件时,显示结果如下：:
	Uploaded File Info:
	
	Sent file: uploadedfile.txt
	File size: 2003 bytes
	File type: image/jpg

你自己在网络服务器上尝试上述例子后，如果您有任何问题，请发到论坛上将得到进一步的帮助。
