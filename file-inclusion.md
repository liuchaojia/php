# PHP文件包含

您可以在一个PHP文件中包含另一个PHP文件的内容，在服务器执行它之前。有两个PHP函数,可用于包括一个PHP文件到另一个PHP文件。

* include() 函数
* require() 函数

这两个函数用于创建可在多个页面重复使用的函数、页眉、页脚或元素。这会为开发者节省大量的时间。这意味着您可以创建供所有网页引用的标准页眉或菜单文件。当页眉需要更新时，您只更新一个包含文件就可以了，或者当您向网站添加一张新页面时，仅仅需要修改一下菜单文件（而不是更新所有网页中的链接）。

## include() 函数

include() 函数可获得指定文件中的所有文本，并把文本拷贝到使用 include 函数的文件中。include() 函数会生成一个警告，但是脚本会继续执行。
  
假设您希望创建一个共同的菜单为您的网站。然后创建一个menu.php使用以下内容。

	<a href="http://www.tutorialspoint.com/index.htm">Home</a> - 
	<a href="http://www.tutorialspoint.com/ebxml">ebXML</a> - 
	<a href="http://www.tutorialspoint.com/ajax">AJAX</a> - 
	<a href="http://www.tutorialspoint.com/perl">PERL</a> <br />

你现在想创建尽可能多的页面,包括这个文件创建标题。例如现在您的test.php文件可以有以下内容。

	<html>
	<body>
	<?php include("menu.php"); ?>
	<p>This is an example to show how to include PHP file!</p>
	</body>
	</html>

这个文件会输出以下结果：

	Home - ebXML - AJAX - PERL 
	
    这是一个示例来展示如何使用PHP文件包含。您可以包含更多你需要包函的菜单，php文件!

## require() 函数
**require()**函数接受的所有文本文件,并将它复制到指定的文件中,使用了包括功能。如果有任何问题在加载一个文件，**require()**函数生成一个致命错误,停止脚本的执行。

**require()** 函数与 include() 相同，不同的是它对错误的处理方式。include() 函数会生成一个警告，但是脚本会继续执行，而 require() 函数会生成一个致命错误（fatal error）在错误发生后脚本会停止执行。
你可以尝试用以上示例include()函数,它会产生相同的结果。但是如果你运行以下两个例子，文件不存在,那么你会得到不同的结果。

	<html>
	<body>
	<?php include("xxmenu.php"); ?>
	<p>This is an example to show how to include wrong PHP file!</p>
	</body>
	</html>

这个文件会输出以下结果：

    This is an example to show how to include wrong PHP file!

现在，让我们使用 require() 函数运行相同的例子。

	<html>
	<body>
	<?php require("xxmenu.php"); ?>
	<p>This is an example to show how to include wrong PHP file!</p>
	</body>
	</html>

这一次文件执行中断并没有显示出任何内容。

**注意:**您可能会得到简单的警告消息或致命错误消息或一无所有。这取决于您的PHP服务器配置。
