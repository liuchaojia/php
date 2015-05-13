# PHP正则表达式

只不过是一个序列或正则表达式模式的字符本身。　　
　　　　　　
正则表达式(regular expression) 只不过是一种字符串匹配的模式，他提供了模式匹配功能的基础。
使用正则表达式可以在一个字符串中搜索一个特定的字符串,你可以在一个字符串中换取另一个字符串,当然你也可以将一个字符串分割成很多块。

PHP提供了两组针对正则表达式的函数,每一个函数对应于一种特定的正则表达式。基于你的需求，您可以使用任何该函数：

* POSIX正则表达式　
* PERL风格正则表达式


## POSIX正则表达式
POSIX正则表达式的结构并没有什么不同的典型的算术表达式:它是由各种元素(运算符)相结合并形成更复杂的正则表达式。
　

最简单的正则表达式就是匹配一个字符,例如g,在gg, haggle或者 bag等字符串内部。

让我们可以先给一些解释性的概念介绍怎么使用POSIX正则表达式。之后,我们将介绍这个正则表达式相关功能。

### 括号
方括号([])是具有特殊意义的在上下文中使用的正则表达式。他们是用来发现一系列字符。

<table class="table table-bordered">
<tr>
<th width="30%">正则表达式  
    
</th><th width="70%">   描述</th>
</tr>
<tr>
<td>[0-9]</td>
<td>匹配任意一个数字从0到9</td>
</tr>
<tr>
<td>[a-z]</td>
<td> 匹配所有的小写字母从a到z </td>
</tr>
<tr>
<td>[A-Z]</td>
<td> 匹配所有的大写字母从A到Z </td>
</tr>
<tr>
<td>[a-Z]</td>
<td>匹配所有的字母从a到Z</td>
</tr>
</table>

上面所示的范围是大致范围;您还可以使用范围[0 – 3]匹配任何十进制数字从0到3的任意一个十进制数字,或范围[b-v]来匹配任何小写字符从字符b到字符v。

### 量词: 　
　　　
括起来的字符序列的频率或位置和单个字符都可以用来表示一个特殊的角色。每个特殊字符都有一个特定的隐含意义。+, *, ?, {int. range}和$ flag都遵循一个字符序列。

<table class="table table-bordered">
<tr>
<th width="30%">正则表达式    

</th><th width="70%"> 描述</th>
</tr>
<tr>
<td>p+</td>
<td>	匹配P的子表达式一次或多次。</td>
</tr>
<tr>
<td>p*</td>
<td>	它匹配包含零个或多个p的任何字符串。</td>
</tr>
<tr>
<td>p?</td>
<td>它匹配包含零个或多个p的任何字符串。这只是另一种方式使用p *。</td>
</tr>
<tr>
<td>p{<b>N</b>}</td>
<td>它匹配N个 p的任何字符串</td>
</tr>
<tr>
<td>p{2,3}</td>
<td>它匹配包含一个序列的两个p或三个p任何字符串。</td>
</tr>
<tr>
<td>p{2, }</td>
<td>	它匹配包含至少两个p的序列的任何字符串。</td>
</tr>
<tr>
<td>p$</td>
<td>	它匹配任何以p结尾的字符串。 
</td>
</tr>
<tr>
<td><b>^</b>p</td>
<td>	它匹配任何以p开头的字符串。</td>
</tr>
</table>
<h3>例子</h3>
<p>下面的例子将会帮助你梳理你的匹配字符的概念。	
</p>
<table class="table table-bordered">
<tr>
<th width="30%">正则表达式</th><th width="70%">说明</th>
</tr>
<tr>
<td>[^a-zA-Z]</td>
<td>它匹配任何不包含从a到z、A到Z的字符的字符串。</td>
</tr>
<tr>
<td>p.p</td>
<td>它匹配任何包含p的字符串,其次是任何字符,紧随其后的是另一个p。</td>
</tr>
<tr>
<td>^.{2}$</td>
<td>它匹配任何包含两个字符的字符串。</td>
</tr>
<tr>
<td>&lt;b&gt;(.*)&lt;/b&gt;</td>
<td>它匹配任何封闭在< b >和< / b >之间的字符串。</td>
</tr>
<tr>
<td>p(hp)*</td>
<td>它匹配任何包含一个字符p紧随其后的零个或多个字符hp的字符串.</td>
</tr>
</table>

### 预定义的字符序列　　　　

为了你编程的方便，预定义了一些可用的字符集,也被称为字符类。字符类是指定一个完整的范围内的字符,例如,字母或一组整数:
	

<table class="table table-bordered">
<tr>
<th width="30%">正则表达式</th><th width="70%">说明</th>
</tr>
<tr>
<td>[[:alpha:]]</td>
<td>它匹配任何包含字母字符从字符aA 到字符zZ 的字符串。</td>
</tr>
<tr>
<td>[[:digit:]]</td>
<td>它匹配任何包含数值数字0到9的字符串。 </td>
</tr>
<tr>
<td>[[:alnum:]]</td>
<td>它匹配任何包含字母字符从字符aA 到字符zZ 和数字0到9的字符串。</td>
</tr>
<tr>
<td>[[:space:]]</td>
<td>它匹配任何包含一个空格的字符串。</td>
</tr>
</table>
## php的posix正则表达式函数


PHP目前提供了七个使用POSIX-style来搜索字符串的正则表达式函数:

<table class="table table-bordered">
<tr>
<th width="30%">
正则表达式	</th><th width="70%">说明</th>
</tr>
<tr>
<td><a href="/php/php_ereg.htm">ereg()</a></td>
<td>函数用指定的模式来搜索指定的字符串中的字符串,成功返回true, ,否则,则返回false。 </td>
</tr>
<tr>
<td><a href="/php/php_ereg_replace.htm">ereg_replace()</a></td>
<td>本函数以 pattern 的规则来解析比对字符串 string，欲取而代之的字符串为参数 replacement。返回值为字符串类型，为取代后的字符串结果。 </td>
</tr>
<tr>
<td><a href="/php/php_eregi.htm">eregi()</a></td>
<td>函数用指定的模式来搜索指定的字符串中的字符串。搜索不区分大小写。</td>
</tr>
<tr>
<td><a href="/php/php_eregi_replace.htm">eregi_replace()</a></td>
<td>本函数和 ereg_replace() 类似，用法也相同。不同之处在于 ereg_replace() 有区分大小写，本函数与大小写无关。
</td>
</tr>
<tr>
<td><a href="/php/php_split.htm">split()</a></td>
<td>函数返回一个字符串数组，每个单元为$string经正则表达式$pattern作为边界分割出的子串。 </td>
</tr>
<tr>
<td><a href="/php/php_spliti.htm">spliti()</a></td>
<td>本函数和 split() 类似，用法也相同。不同之处在于 split()有区分大小写，本函数与大小写无关 </td>
</tr>
<tr>
<td><a href="/php/php_sql_regcase.htm">sql_regcase()</a></td>
<td>sql_regcase()函数可以被认为是一个效用函数, 返回的表达式是将 string 中的每个字母字符转换为方括号表达式，该方括号表达式包含了该字母的大小写形式。</td>
</tr>
</table>


## PERL风格正则表达式: 　　　　
Perl-style正则表达式类似于POSIX正则表达式。POSIX语法与Perl-style正则表达式函数语法相似几乎可以互换。事实上,您可以使用任何前面的POSIX小节中介绍的量词。　　

让我们可以给一些概念解释被用于PERL的正则表达式。之后,我们将介绍这个正则表达式相关功能。

### 元字符

元字符只是一个字母字符，在元字符之前加入一个反斜杠,给组合特别的意义。

例如,您可以使用“\ d”元字符：/([\d]+)000/搜索大量资金总额,这里\ d将在任何的字符串中寻找数值字符。

下面是元字符的列表,可以使用PERL风格的正则表达式。

	字符	      	  说明
	.       一个字符
	\s：    用于匹配单个空格符，包括tab键和换行符；
	\S：    用于匹配除单个空格符之外的所有字符；
	\d：    用于匹配从0到9的数字；
	\D：    用于匹配没有数字的所有字符；
	\w：    用于匹配字母，数字或下划线字符(a-z, A-Z, 0-9, _)；
	\W：    用于匹配所有与\w不匹配的字符；
	[aeiou]        在给定的集合内匹配一个字符
	[^aeiou]       在给定的集合外匹配一个字符
	(foo|bar|baz)  匹配任何指定的备选方案


### 修饰符

使用几个regexp修饰符,它能使你的工作更容易,比如字母大小写敏感性、搜索多个行等等。

	修饰符	说明
	i 在和正则匹配是不区分大小写 
	m 将字符串视为多行。默认的正则开始“^”和结束“$”将目标字条串作为一单一的一“行”字符（甚至其中包括换行符也是如此）。如果在修饰符中加上“m”，那么开始和结束将会指点字符串的每一行的开头就是“^”结束就是“$”。 
	o 	评估表达式只有一次
	s 如果设定了这个修正符，那么，被匹配的字符串将视为一行来看，包括换行符，换行符将被视为普通字符串。 
	x 忽略空白，除非进行转义的不被忽略。 
	g 	在全局范围内找到所有匹配
	cg 	即使全局匹配失败也允许搜索继续

## PHP的Regexp PERL兼容函数

PHP提供了以下函数使用perl的正则表达式来搜索字符串


	函数             	说明
	preg_match()      执行一个正则表达式匹配，成功返回true，否则返回 false。 
	preg_match_all()  执行一个全局正则表达式匹配
	preg_replace()    使用preg_replace()函数和使用函数ereg_replace()类似,除了可以使用正则               表达式的模式和替换外还可以输入参数
	preg_split()      使用preg_split()函数和使用函数split()类似,除此之外还接受正则表达式模式作为输入的参数
	preg_grep()       preg_grep()函数搜索input_array的所有元素,返回所有匹配正则表达式模式的元素。
	preg_ quote()     引用正则表达式字符



