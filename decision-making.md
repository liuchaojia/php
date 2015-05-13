# PHP结构控制

if,elseif…else和switch语句是用来根据不同的条件决定结构控制。

您可以在代码中使用条件语句,让你决定结构控制。PHP支持三种结构控制发表声明:


* **if...else**语句 – 使用这种语句的场景：当条件为 true 时，执行一块代码；当条件为 false 时，执行另一块代码。
* 
elseif 语句 -与 if...else 配合使用，在若干条件之一为真时执行一个代码块。
* switch 语句 - 如果您希望有选择地执行若干代码块之一，请使用 Switch 语句。使用 Switch 语句可以避免冗长的 if..elseif else 代码块。

## If...Else 语句

如果你想要执行一些代码如果条件为真,另一个代码是条件为假的,如果条件为假，使用If...Else 语句。



### 语法

    if (_condition_)
    code to be executed if condition is true;_
    else
    code to be executed if condition is false;_

### 例子

下面的例子  如果当前日期是周五，下面的代码将输出 "Have a nice weekend!"，否则会输出 "Have a nice day!"：

	<html>
	<body>
	<?php
	$d=date("D");
	if ($d=="Fri")
	  echo "Have a nice weekend!"; 
	else
	  echo "Have a nice day!"; 
	?>
	</body>
	
	</html>

    
如果条件为真/假并且超过一行的应该被执行,这些代码行应该包含在花括号内:

	    
	<html>
	
	<body>
	<?php
	$d=date("D");
	if ($d=="Fri")
	  {
	  echo "Hello!<br />"; 
	  echo "Have a nice weekend!";
	  echo "See you on Monday!";
	  }
	?>
	</body>
	</html>

    
       
        
    

## ElseIf 语句
如果您希望在某个条件为真时执行一些代码，请使用 ElseIf 语句。




### 语法

    if (_condition_)
    code to be executed if condition is true;_
    elseif (_condition_)
    code to be executed if condition is true;
    else
    code to be executed if condition is false;_

### 例子

如果当前日期是周五，下面的例子中代码将输出 "Have a nice weekend !"，如果当前日期是周日，否则会输出 "Have a nice day!"：

	<html>
	<body>
	<?php
	$d=date("D");
	if ($d=="Fri")
	  echo "Have a nice weekend!"; 
	elseif ($d=="Sun")
	  echo "Have a nice Sunday!"; 
	else
	  echo "Have a nice day!"; 
	?>
	</body>
	</html>


    
    
        
        
    

## Switch 语句

如果您希望有选择地执行若干代码块之一，请使用 Switch 语句。

使用 Switch 语句可以避免冗长的 if..elseif..else 代码块。

### 语法

	switch (expression)
	{
	case label1:
	  code to be executed if expression = label1;
	  break;  
	case label2:
	  code to be executed if expression = label2;
	  break;
	default:
	  code to be executed
	  if expression is different 
	  from both label1 and label2;
	
	}
### 例子

switch语句的工作的方式在不同寻常。首先它根据表达式中的值然后寻求匹配标签的结果值。如果找到一个值匹配那么与匹配标签相关联的代码将被执行或者没有和表达式的值相匹配的语句将会执行指定的default代码。

	<html>
	<body>
	<?php
	$d=date("D");
	switch ($d)
	{
	case "Mon":
	  echo "Today is Monday";
	  break;
	case "Tue":
	  echo "Today is Tuesday";
	  break;
	case "Wed":
	  echo "Today is Wednesday";
	  break;
	case "Thu":
	  echo "Today is Thursday";
	  break;
	case "Fri":
	  echo "Today is Friday";
	  break;
	case "Sat":
	  echo "Today is Saturday";
	  break;
	case "Sun":
	  echo "Today is Sunday";
	  break;
	default:
	  echo "Wonder which day is this ?";
	}
	?>
	</body>
	</html>

