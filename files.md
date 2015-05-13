# PHP文件&I / O
本章将解释以下函数相关文件:

* 打开一个文件
* 阅读一个文件
* 写一个文件
* 关闭一个文件


## 打开和关闭一文件
PHP fopen()函数用于打开一个文件。它需要两个参数声明文件名称和操作模式。

可以指定文件模式的六个选项在这个表。

<table class="table table-bordered">
<tr>
<th width="20%">
模式	
</th>
<th width="80%">
用法
</th>
</tr>
<tr>
<td>
r
</td>
<td>打开文件仅供阅读。将指针放到文件的开头。






</p>
</td>
</tr>
<tr>
<td>
r+
</td>
<td>
打开文件进行阅读和写作。将指针放到文件的开头。</p>
</td>
</tr>
<tr>
<td>
w
</td>
<td>
打开文件仅供编写。将指针放到文件的开头。如果文件不存在它将创建一个文件存在。
</td>
</tr>
<tr>
<td>
w+
</td>
<td>
打开文件仅供阅读和写作。将指针放到文件的开头。如果文件不存在它将创建一个文件存在。
</td>
</tr>
<tr>
<td>
a
</td>
<td>
打开文件仅供编写。将指针放到文件的结尾。如果文件不存在它将创建一个文件存在。
</td>
</tr>
<tr>
<td>
a+
</td>
<td>

打开文件仅供阅读和写作。将指针放到文件的结尾。如果文件不存在它将创建一个文件存在。
</td>
</tr>
</table>
如果试图打开一个文件失败然后fopen返回一个false值,否则它返回一个文件指针用于进一步阅读或写文件。

打开文件做出更改之后使用fclose()函数关闭它是很重要的。fclose()函数需要一个文件指针作为参数,然后关闭成功返回true，如果关闭不能成功返回假。

## 阅读文件
一旦使用fopen()函数打开一个文件可以调一个函数fread()用于读文件。这个函数需要两个参数。这些参数都是必须的，文件指针和文件表示的长度字节。

文件的长度可以使用filesize()函数，此函数将文件名作为参数,并返回文件用字节所表示的大小。

这里是用PHP读取文件所需的步骤。　　　　

* 打开一个文件使用fopen()函数。　　　　
* 得到文件的长度使用filesize()函数。　　　　
* 读取文件的内容使用fread()函数。　　　　
* 关闭文件和fclose()函数。


下面的例子将文本文件的内容赋给一个变量然后在web页面上显示这些内容。

	<html>
	<head>
	<title>Reading a file using PHP</title>
	</head>
	<body>
	
	<?php
	$filename = "/home/user/guest/tmp.txt";
	$file = fopen( $filename, "r" );
	if( $file == false )
	{
	   echo ( "Error in opening file" );
	   exit();
	}
	$filesize = filesize( $filename );
	$filetext = fread( $file, $filesize );
	
	fclose( $file );
	
	echo ( "File size : $filesize bytes" );
	echo ( "<pre>$filetext</pre>" );
	?>
	
	</body>
	</html>

## 写一个文件
使用PHP fwirte()函数可以编写一个新文件或文本到附加的现有文件里。该函数需要两个参数指定一个文件指针的字符串被写入的数据。可选的第三个整数参数可以包含指定写入数据的长度。如果第三个参数被包含,指定的长度写完后操作就会停止。

下面的示例创建一个新的文本文件然后在里面写一个简短的文本标题。关闭这个文件后它的存在与否可以使用file_exist()函数并且将文件名作为参数。

	<?php
	$filename = "/home/user/guest/newfile.txt";
	$file = fopen( $filename, "w" );
	if( $file == false )
	{
	   echo ( "Error in opening new file" );
	   exit();
	}
	fwrite( $file, "This is  a simple test\n" );
	fclose( $file );
	?>
	
	<html>
	<head>
	<title>Writing a file using PHP</title>
	</head>
	<body>
	
	<?php
	if( file_exist( $filename ) )
	{
	   $filesize = filesize( $filename );
	   $msg = "File  created with name $filename ";
	   $msg .= "containing $filesize bytes";
	   echo ($msg );
	}
	else
	{
	   echo ("File $filename does not exit" );
	}
	?>
	</body>
	</html>

我们已经介绍了所有相关的文件函数输入和PHP系统函数章节。






If an attempt to open a file fails then **fopen** returns a value of **false** otherwise it returns a **file pointer** which is used for further reading or writing to that file.

After making a changes to the opened file it is important to close it with the **fclose()** function. The **fclose()** function requires a file pointer as its argument and then returns **true** when the closure succeeds or **false** if it fails.

## Reading a file

Once a file is opened using **fopen()** function it can be read with a function called **fread()**. This function requires two arguments. These must be the file pointer and the length of the file expressed in bytes.

The files's length can be found using the **filesize()** function which takes the file name as its argument and returns the size of the file expressed in bytes.

So here are the steps required to read a file with PHP.

* Open a file using **fopen()** function.
* Get the file's length using **filesize()** function.
* Read the file's content using **fread()** function.
* Close the file with **fclose()** function.

The following example assigns the content of a text file to a variable then displays those contents on the web page.

    
    
    
    
    

    

    
    

## Writing a file

A new file can be written or text can be appended to an existing file using the PHP **fwrite()** function. This function requires two arguments specifying a **file pointer** and the string of data that is to be written. Optionally a third integer argument can be included to specify the length of the data to write. If the third argument is included, writing would will stop after the specified length has been reached.

The following example creates a new text file then writes a short text heading insite it. After closing this file its existence is confirmed using **file_exist()** function which takes file name as an argument

    

    
    
    
    
    

    
    
    

We have covered all the function related to file input and out in [PHP File System Function][1] chapter.

