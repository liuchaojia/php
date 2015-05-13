
# PHP运算符类型

**运算符是什么?**简单的答案可以使用表达式4 + 5等于9。这里4和5被称为操作数和+号叫做运算符。

PHP语言支持以下类型的运算符。.

* 算术运算符
* 比较运算符
* 逻辑(或关系) 运算符
* 赋值运算符
* 条件赋值操作符(或三元) 运算符

让我们接下来一个个的看运算符的操作。

## 算术运算符

有以下算术运算符支持PHP语言:

假设变量 A赋值10和变量B赋值20:

显示以下例子

<table class="table table-bordered">
<tr>
<th width="20%">运算符</th><th width="35%">说明</th><th>例子</th>
</tr>
<tr>
<td>+</td><td>变量A和变量B相加</td><td> A + B 等于 30</td>
</tr>
<tr>
<td>-</td><td>变量A和变量B相减</td><td> A - B等于-10</td>
</tr>
<tr>
<td>*</td><td>变量A和变量B相乘</td><td> 	A * B等于 200</td>
</tr>
<tr>
<td>/</td><td>变量A和变量B相除</td><td>	B / A等于2</td>
</tr>
<tr>
<td>%</td><td>变量A和变量B取余数</td><td>	B % A等于0</td>
</tr>
<tr>
<td>++</td><td>变量A++
	
</td><td>	A++等于11</td>
</tr>
<tr>
<td>--</td><td>变量A--</td><td> A--等于9</td>
</tr>

</table>

## 比较运算符:


有以下比较运算符支持PHP语言:假设变量 A赋值10和变量B赋值20:

显示以下例子

<table class="table table-bordered">
<tr>
<th width="20%">运算符</th><th width="35%">说明</th><th>例子</th>
</tr>
<tr>
<td>==</td><td>检查两个操作数的值是否相等,如果相等,那么条件变为真。	 



 

</td><td>(A == B) 是不为真的.</td>
</tr>
<tr>
<td>!=</td><td>检查两个操作数的值是否相等,如果值不相等,那么条件变为真。 </td><td>	(A != B) 为真.</td>
</tr>
<tr>
<td>&gt;</td><td>检查左操作数的值是否大于右操作数的值,如果是的,那么条件变为真。	 </td><td>(A > B) 为假.</td>
</tr>
<tr>
<td>&lt;</td><td>检查左操作数的值小于右操作数的值,如果是的,那么条件变为真。	 </td><td>(A < B) 为真.</td>
</tr>
<tr>
<td>&gt;=</td><td>检查左操作数的值是否大于或等于右操作数的值,如果是的,那么条件变为真。	</td><td> (A >= B) 为假.</td>
</tr>
<tr>
<td>&lt;=</td><td>检查左操作数的值是否小于或等于右操作数的值,如果是的,那么条件变为真。	 </td><td>(A <= B) 为真.</td>
</tr>
</table>

## 逻辑运算符: 
有以下逻辑运算符支持PHP语言:假设变量 A赋值10和变量B赋值20:

显示以下例子

<table class="table table-bordered">
<tr>
<th width="20%">运算符</th><th width="35%">说明</th><th>例子</th>
</tr>
<tr>
<td>and</td><td>称为逻辑与操作。如果两个操作数都是真的,那么条件变成真。	



</td><td>(A and B) 为真.</td>
</tr>
<tr>
<td>or</td><td>称为逻辑或运算符。如果两个操作数的任何一个非零,那么情况就变为真。	</td><td> (A or B) 为真.</td>
</tr>
<tr>
<td>&amp;&amp;</td><td> 称为逻辑与操作。如果两个操作数都非零然后条件变成真。	 </td><td> (A && B) 为真. </td>
</tr>
<tr>
<td>||</td><td>称为逻辑或运算符。如果两个操作数的都不为零,那么情况就变为真。	</td><td> (A || B) 为真。</td>
</tr>
<tr>
<td>!</td><td>称为逻辑非。使用反转逻辑状态的操作数。如果是真的,那么一个条件逻辑操作符将是假的。	 </td><td> !(A && B) 为假. </td>
</tr>
</table>

## 赋值运算符

有以下赋值运算符由PHP语言支持


显示以下例子



<table class="table table-bordered">
<tr>
<th width="20%">运算符</th><th width="35%">说明</th><th>例子</th>
</tr>
<tr>
<td>=</td><td>简单的赋值运算符,将来自右操作数的值赋给左边的操作数	 





</td><td> C = A + B 将赋值给C赋值 A + B </td>
</tr>
<tr>
<td>+=</td><td>添加和赋值运算符,它将右操作数与左操作数的求和结果分配给左操作数	</td><td> C += A 等于 C = C + A</td>
</tr>
<tr>
<td>-=</td><td>减去和赋值运算符,右操作数减去左操作数,并将结果分配给左操作数	</td><td>C -= A 等于 C = C - A</td>
</tr>
<tr>
<td>*=</td><td>相乘和赋值运算符,它可以使右操作数乘以左操作数,并将结果分配给左操作数	</td><td> C *= A 等于 C = C * A</td>
</tr>
<tr>
<td>/=</td><td>相除和赋值运算符,将左操作数除以右操作数,并将结果分配给左操作数	</td><td> C /= A 等于 C = C / A</td>
</tr>
<tr>
<td>%=</td><td>取模和赋值运算符, 将左操作数除以右操作数的余数分配到左操作数的结果	</td><td> C %= A 等于 C = C % A</td>
</tr>
</table>


## 条件运算符

还有一个运算符称为条件运算符。这第一次评估一个表达式为真或假值,然后根据评价的结果执行两个给定的语句。条件运算符有这种语法:

显示以下例子


<table class="table table-bordered">
<tr>
<th width="20%">运算符</th><th width="35%">说明</th><th>例子</th>
</tr>
<tr>
<td>? :</td><td>条件表达式</td><td> 	条件为真则返回？号后面的值否则返回：号后面的值</td>
</tr>
</table>

## 运算符分类


我们上文已经讨论过的所有运算符可分为以下类别:

* 一元前缀运算符,优先操作一个操作数。
* 二元运算符,这两个操作数,执行各种算术和逻辑操作。
* 条件操作符(三元操作符),将三个操作数,计算第二个或第三个表达式,根据评估的第一个表达式。
* 赋值操作符,将值分配给一个变量。



## 运算符优先级

运算符优先级确定条件表达式的分组。这会影响如何评估一个表达式。某些运算符比其他运算符有更高的优先级,例如,乘法运算符的优先级高于加法运算符:

例如x = 7 + 3 * 2,这里x是13,不是20因为运算符*的优先级高于+所以首先获得乘以3 * 2,然后添加到7。

在这里运算符优先级最高的出现在表的顶部,底部是出现优先级最低的。在一个表达式,更高的优先级运算符将被评估。

<table class="table table-bordered">
<tr><th>运算符类别 &nbsp;</th>
<th> 运算符&nbsp;</th>
<th> 	关联性&nbsp;</th>
</tr> 
<tr>
<td>Unary&nbsp;</td>
<td>! ++ --&nbsp;</td> 
<td>从右往左 
&nbsp;</td>
</tr>
<tr>
<td>Multiplicative &nbsp;</td> 
<td>*  /  %&nbsp;</td>
<td>从左向右&nbsp;</td> 
</tr> 
<tr> 
<td>Additive &nbsp;</td>
<td>+  -&nbsp;</td> 
<td>从左向右&nbsp;</td> 
</tr>
<tr> 
<td>Relational &nbsp;</td>
<td>&lt; &lt;=  &gt; &gt;=&nbsp;</td> 
<td>从左向右&nbsp;</td> 
</tr>
<tr> 
<td>Equality &nbsp;</td> 
<td>==  !=&nbsp;</td> 
<td>从左向右&nbsp;</td> 
</tr> 
<tr> 
<td>Logical AND&nbsp;</td>
<td>&amp;&amp;&nbsp;</td> 
<td>从左向右&nbsp;</td> 
</tr> 
<tr>
<td>Logical OR&nbsp;</td> 
<td>||&nbsp;</td> 
<td>从左向右&nbsp;</td> 
</tr> 
<tr> 
<td>Conditional&nbsp;</td>
<td>?:&nbsp;</td> 
<td>从右往左 &nbsp;</td> 
</tr> 
<tr>
<td>Assignment&nbsp;</td> 
<td>=  +=  -=  *=  /=  %=</td> 
<td>从右往左 &nbsp;</td>
</tr> 
</table>

