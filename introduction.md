# PHP 介绍
PHP 开始仅作为一个小的开放源码项目，现在越来越多的人发现它非常实用。早在 1994 年，Rasmus Lerdorf开发出第一版本 PHP。

*   PHP 是递归首字母缩写"PHP： Hypertext Preprocessor "

*   PHP 是嵌入在 HTML 中的服务器端脚本语言。它用来管理动态内容、 数据库、 会话跟踪，甚至建立整个电子商务网站。

*  它集成了许多流行的数据库，包括 MySQL、 PostgreSQL、 Oracle、 Sybase、 Informix和Microsoft SQL Server。

*   尤其在Unix系统里PHP作为 Apache编译模块时，PHP 有令人欣喜的执行力。一旦开始，MySQL 服务器将在设定的时间内执行非常复杂的命令查询巨大的结果集。

*   PHP 支持一大批主要协议，如 POP3、 IMAP 和 LDAP。PHP4 添加了对 Java 的支持，并且首次分布对象体系结构 （COM 和 CORBA），并制作多层开发。

*   PHP 语言简洁： PHP 语言系统要求不需要太严谨。

*  PHP 语法类似 C语言。
*  
## PHP 的常见用途：

*   PHP 执行系统功能，它可以创建、 打开、 读、 写和关闭系统上的文件。

*   PHP 可以处理forms表单，如收集数据文件，将数据保存到一个文件中，可以通过电子邮件发送数据，返回给用户数据。

*   通过 PHP在数据库中添加、 删除、 修改元素。

*   访问 cookie 变量和设置 cookie。

*   使用 PHP，您可以限制用户访问您的网站的某些页面。

*   它可以对数据进行加密。
*   
## PHP 的特点

PHP普及的五个重要特征：

*   简单

*   效率

*   安全

*   灵活性

*   多便

## PHP（Hello World）脚本：

为了了解PHP,先从简单的PHP脚本开始。 “Hello, World!”是一个基本的例子,首先,我们将创建一个友好的“Hello, World!”小脚本。

正如前面提到的,PHP是嵌入在HTML中。这意味着在你正常的HTML(或XHTML如果你很先进)你有PHP语句如下：
	
	
	<html>
	<head>
	<title>Hello World</title>
	<body>
	    <?php echo "Hello, World!";?>
	</body>
	</html>

它将会输出以下结果：

	Hello, World!

若要检查上面例子中HTML 输出，您会注意到 PHP 代码不是本文件从服务器发送到Web浏览器中。所有的 PHP在 Web 页中呈现处理和脱离状态；从 Web 服务器向客户端返回的唯一的方式就是纯粹HTML输出。

所有PHP代码必须包括三个特别标记之一才可被PHP解析器认可。


	<?php PHP code goes here ?>
	
	<?    PHP code goes here ?>
	
	<script language="php">PHP code goes here </script>


最常见的标签是 <? Php…?> 同时我们的教程中还将使用相同的标记。

从下一章节我们将开始在您的计算机上设置PHP 环境，为了让你适应 PHP 语言我们会深入探讨几乎所有与PHP相关的概念。
