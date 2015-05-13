# PHP 语法概述

这一章将给你介绍下基本的PHP语法，对增强你的PHP的基础非常重要。

## php 解析：

PHP解析引擎需要一种方法来区分其他页面中的PHP代码。这样的机制被称为PHP解析。有四个方式可以去解析：
### 典范的PHP标签：

最普遍有效的PHP标记风格是：  <?php...?>
如果你使用这种风格，可以确保你的标签将被正确的解析。

### 短标签形式（SGML形式）标签：

短标签如下所示：
<?...?>

短标签,正如你所预料的那样,最短的选项。你必须做两件事中的一件,使PHP识别标签:

*	当你构建PHP时，选择--enable-short-tags配置选项。

*	在php.ini文件设置short_open_tag为on。PHP配置文件中必须禁用此选项防止解析XML，因为相同的语法适用于XML标记。

### ASP风格的标签：

asp风格标签被用在动态服务器页面定义代码块。asp风格标记看起来像这样:
<%...%>

使用asp风格标签,您将需要在php中设置php.ini文件中的配置选项。

### HTML 脚本标签：

HTML 脚本标签如下所示：

	<script language="PHP">...</script>

## PHP代码的注释：

注释是程序的一部分,为了在程序执行显示结果之前帮助读者解读代码。在PHP中有两种注释：

单行注释:他们通常用于对相关的本地代码做简短解释或笔记。这是单行注释的例子。
	
	<?
	
	 # This is a comment, and
	
	 # This is the second line of the comment
	
	// This is a comment too. Each style comments only
	
	print "An example with single line comments";
	
	?>

多行注释:下面的例子用一个print语句来打印多行:

	<?
	 
	 # First Example
	
	 print <<<END
	
	 This uses the "here document" syntax to output
	
	 multiple lines with $variable interpolation. Note
	
	 that the here document terminator must appear on a
	
	 line with just a semicolon no extra whitespace!
	
	 END;
	 # Second Example
	
	 print "This spans
	
	 multiple lines. The newlines will be
	
	 output as well";
	
	?>

多行注释:他们通常在必要时用来为代码提供算法和更详细的解释。多行注释风格和在C语言中是一样的，下面有多行注释的例子。

	<?
	
	/* This is a comment with multiline
	
	    Author : Mohammad Mohtashim
	
	    Purpose: Multiline Comments Demo
	
	    Subject: PHP
	
	*/
	
	print "An example with multi line comments";
	
	?>


## PHP对空格不敏感

空格在你输入的屏幕上通常是看不见的,包括空格、制表符、回车(行尾字符)。

PHP对空格不敏感,这意味着在PHP中你有多少空白字符对你没有影响。一个空格就相当于一个字符一样。

例如,以下任何一个PHP语句把2+2的总和赋给变量$four求值是相等的。

	$four = 2 + 2; // single spaces
	
	$four <tab> = <tab2<tab><tab> + <tab>2 ; // spaces and tabs
	
	$four =
	
	2+
	
	2; // multiple lines

## PHP是大小写敏感的:：

是的，没错，PHP是一种大小写敏感的语言。试试下面的例子:

	<html>
	<body>
	<?
	$capital = 67;
	print("Variable capital is $capital<br>");
	print("Variable CaPiTaL is $CaPiTaL<br>");
	?>
	</body>
	</html>

这将会输出以下内容：

	Variable capital is 67
	Variable CaPiTaL is

## 语句表达式由分号终止:

PHP的任何表达式语句后面的是一个分号(;)。任何在PHP标签里有效的PHP语句都是有效的PHP程序，下面的语句在PHP中是一个典型的语句,在这种情况下将字符串赋值给一个名为$greeting的变量:

	$greeting = "Welcome to PHP!";

## 表达式的组合令牌:

最小的PHP的构建模块是不可分割的令牌,如数字(3.14159),字符串(.two.)，变量($two),常量(TRUE),和特殊的单词构成的PHP语法本身,像if, else, while, for and so forth。

## 花括号组成代码块：

虽然语句不能像表达式那样相结合,你可以在任何地方把一系列语句包含在一组花括号内。

下面这两个语句是等价的：

	if (3 == 2 + 1)
	  print("Good - I haven't totally lost my mind.<br>");
	
	if (3 == 2 + 1)
	{
	   print("Good - I haven't totally");
	   print("lost my mind.<br>");
	}

## 在命令提示符中运行PHP脚本	

是的,你可以在你的命令提示符里运行PHP脚本。假设您已经有下面的test.php文件

	<?php
	   echo "Hello PHP!!!!!";
	?>

现在在命令提示符里运行这个脚本如下:

	$ php test.php

脚本将会输出以下内容：

	Hello PHP!!!!!

希望你现在具有PHP语法的基本知识

