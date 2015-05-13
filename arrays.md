# PHP 数组

数组是一种数据结构, 数组能够在单独的变量名中存储一个或多个值。将一个或多个类似的值存储在一个单独的变量名中。例如如果你想储存100个数字你可以定义一个数组长度为100的变量。

有三种不同类型的数组, 数值数组存储的每个元素都带有一个数字 ID 键。可以使用不同的方法来创建数值数组：

* **数字数组** \-数组以一个数字作为索引。值在线性中存储和访问。
* **关联数组** \-数组以字符串作为索引。这个数组存储元素值与键值不是一个严格的线性索引顺序。
* **多维数组** \-包含一个或多个数组，数组值可以使用多个索引访问

注意:内置数组函数给出了很多函数参考在PHP数组函数库里。


## 索引数组

这些数组可以存储数字、字符串和任何对象但是他们将数字作为索引。默认情况下,数组索引从0开始。

### 例子
    
下面的例子显示了如何创建和访问一个索引数组。

在这里我们使用**array()**函数创建数组。这个函数在函数参考中有说明

	<html>
	<body>
	<?php
	/* First method to create array. */
	$numbers = array( 1, 2, 3, 4, 5);
	foreach( $numbers as $value )
	{
	  echo "Value is $value <br />";
	}
	/* Second method to create array. */
	$numbers[0] = "one";
	$numbers[1] = "two";
	$numbers[2] = "three";
	$numbers[3] = "four";
	$numbers[4] = "five";
	
	foreach( $numbers as $value )
	{
	  echo "Value is $value <br />";
	}
	?>
	</body>
	</html>
	   
	    
	  
上述代码将会输出以下代码：
	
	Value is 1
	Value is 2
	Value is 3
	Value is 4
	Value is 5
	Value is one
	Value is two
	Value is three
	Value is four
	Value is five


## 关联数组

数值数组和关联数组功能非常的相似,他们只是有不同的索引。关联数组将字符串作为索引，这样您就可以建立一个强大的键和值的结构体系。

可以将员工的工资存储在一个数组,用数字索引定义数组并不是最好的选择。相反,我们可以使用员工的名字作为关联数组的键,将工资作为键的值。

**注意:** 不要在关联数组内使用双引号,否则打印它不会返回任何值。


### 例子
   
	<html>
	<body>
	<?php
	/* First method to associate create array. */
	$salaries = array( 
			   "mohammad" => 2000, 
			   "qadir" => 1000, 
			   "zara" => 500
			  );
	
	echo "Salary of mohammad is ". $salaries['mohammad'] . "<br />";
	echo "Salary of qadir is ".  $salaries['qadir']. "<br />";
	echo "Salary of zara is ".  $salaries['zara']. "<br />";
	
	/* Second method to create array. */
	$salaries['mohammad'] = "high";
	$salaries['qadir'] = "medium";
	$salaries['zara'] = "low";
	
	echo "Salary of mohammad is ". $salaries['mohammad'] . "<br />";
	echo "Salary of qadir is ".  $salaries['qadir']. "<br />";
	echo "Salary of zara is ".  $salaries['zara']. "<br />";
	?>
	</body>
	</html>

    

上述代码将会输出以下代码：

    Salary of mohammad is 2000
    Salary of qadir is 1000
    Salary of zara is 500
    Salary of mohammad is high
    Salary of qadir is medium
    Salary of zara is low

## 多维数组

在多维数组中，主数组中的每个元素也是一个数组。在子数组中的每个元素也可以是数组等等，多维数组中的值是使用多个索引访问。

### 例子

在这个示例中,我们创建了一个二维数组在在三个主题中存储三个学生的标志:

这个例子是一个关联数组,您可以以相同的方式创建数值数组。
	
	<html>
	<body>
	<?php
	   $marks = array( 
			"mohammad" => array
			(
			"physics" => 35,	    
			"maths" => 30,	    
			"chemistry" => 39	    
			),
			"qadir" => array
	                (
	                "physics" => 30,
	                "maths" => 32,
	                "chemistry" => 29
	                ),
	                "zara" => array
	                (
	                "physics" => 31,
	                "maths" => 22,
	                "chemistry" => 39
	                )
		     );
	   /* Accessing multi-dimensional array values */
	   echo "Marks for mohammad in physics : " ;
	   echo $marks['mohammad']['physics'] . "<br />"; 
	   echo "Marks for qadir in maths : ";
	   echo $marks['qadir']['maths'] . "<br />"; 
	   echo "Marks for zara in chemistry : " ;
	   echo $marks['zara']['chemistry'] . "<br />"; 
	?>
	</body>
	</html>
	    
    
    

上述代码将会输出以下代码：

    Marks for mohammad in physics : 35
    Marks for qadir in maths : 32
    Marks for zara in chemistry : 39

