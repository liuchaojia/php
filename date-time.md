# PHP日期和时间

日期是的日常生活中常见一部分,就容易不假思索地与时间想在一起。PHP还提供了强大的工具函数来简化操作日期的时间计算.

## 用time()函数得到时间戳：

PHP的time()函数会返回给你所当前的日期和时间，它不需要参数,但返回一个整数。

time()函数返回的整数代表自1970年1月1日午夜格林尼治时间到现在经过的秒数。这一刻被称为UNIX新纪元,之后经过的秒数,被称为一个时间戳。

	<?php
	print time();
	?>

他将会产生以下结果

	948316201
   

It will produce following result:

    948316201

这是很难理解的。但是PHP提供了优秀的工具来将一个时间戳转换成人类熟悉的一种形式。

## 用getdate（）函数来转换时间戳：

获取当前日期getdate()函数可以接受一个时间戳,并返回一个关联数组,其中就包含关于日期的信息。如果你省略了时间戳, time()返回当前的时间戳。

下表列出了函数getdate()返回的数组元素中的单元。

	
	键名	             说明	                     返回值例子
	"seconds"	秒的数字表示（0 到 59）	             20
	"minutes"	分钟的数字表示（0 到 59）	             29
	"hours"	    小时的数字表示(0 - 23)	               22
	"mday"	    月份中第几天的数字表示(1 - 31)      	11
	"wday"	    星期中第几天的数字表示	                4
	"mon"	    月份的数字表示(1 - 12)	               7
	"year"	    4 位数字表示的完整年份(4 digits)	    1997
	"yday"	    一年中第几天的数字表示( 0 - 365 )	    19
	"weekday"	星期几的完整文本表示hursday
	"month"	    月份的完整文本表示January
	0	        时间戳	                           948370048

现在你已经完全掌握了日期和时间函数。你可以得到任何你想得到的日期和时间格式。

## 例子

试运行下面的例子：

	<?php
	$date_array = getdate();
	foreach ( $date_array as $key => $val )
	{
	   print "$key = $val<br />";
	}
	$formated_date  = "Today's date: ";
	$formated_date .= $date_array[mday] . "/";
	$formated_date .= $date_array[mon] . "/";
	$formated_date .= $date_array[year];
	
	print $formated_date;
	?>

将会产生以下结果：
	
	seconds = 27
	minutes = 25
	hours = 11
	mday = 12
	wday = 6
	mon = 5
	year = 2007
	yday = 131
	weekday = Saturday
	month = May
	0 = 1178994327
	Today's date: 12/5/2007


## Example

Try out following example

     $val )
    {
       print "$key = $val";
    }
    $formated_date  = "Today's date: ";
    $formated_date .= $date_array[mday] . "/";
    $formated_date .= $date_array[mon] . "/";
    $formated_date .= $date_array[year];

    print $formated_date;
    ?>

It will produce following result:

    seconds = 27
    minutes = 25
    hours = 11
    mday = 12
    wday = 6
    mon = 5
    year = 2007
    yday = 131
    weekday = Saturday
    month = May
    0 = 1178994327
    Today's date: 12/5/2007

## 用date()函数把时间戳转化成日期：

date()函数返回一个格式化字符串代表一个日期。你可以练习大量的转换格式函数操作,date()函数返回一个字符串。

	date(format,timestamp)
date (格式、时间戳)选择接受一个时间戳作为第二个参数，如果忽落掉第二个参数，那么将会使用当前的时间戳作为参数。

下表列出了一个格式字符串可以包含的代码:


格式 	     说明                              返回值例子

a	小写的上午和下午值                    	下午

A	大写的上午和下午值	                    下午

d	月份中的第几天，有前导零的 2 位数字	    01 到 31

D	星期中的第几天，文本表示，3 个字母	    Mon 到 Sun

j	月份中的第几天，没有前导零	            1 到 31

F	月份名称                          	January 到 December

h	小时，12 小时格式，有前导零	        01 到 12

H	小时，24 小时格式，有前导零	        00 到 23

g	小时，12 小时格式，没有前导零	        1 到 12

G	小时，24 小时格式，没有前导零	        0 到 23

i	有前导零的分钟数	                    00 到 59>

j	一月里的天数                       	20

l（“L”的小写字母）星期几，完整的文本格式	   Sunday 到 Saturday

L	是否为闰年	如果是闰年为 1，否则为 0

m	数字表示的月份，有前导零	01 到 12

M	三个字母缩写表示的月份	Jan 到 Dec

r	RFC 822 格式的日期	例如：Thu, 21 Dec 2000 16:01:07 +0200

n	数字表示的月份，没有前导零	1 到 12

s	秒数，有前导零	00 到 59>

U	从 Unix 纪元（January 1 1970 00:00:00 GMT）开始至今的秒数	参见 time()

y	2 位数字表示的年份	例如：99 或 03

Y	4 位数字完整表示的年份	例如：1999 或 2003

z	年份中的第几天	0 到 366

## 例子

试运行下面的例子：

	<?php
	print date("m/d/y G.i:s<br>", time());
	print "Today is ";
	print date("j of F Y, \a\\t g.i a", time());
	?>

产生结果如下：

	01/20/00 13.27:55

希望你有很好的理解根据您的需求如何格式化日期和时间。供您参考的所有日期和时间函数的完整列表中给出了PHP日期与时间函数。
