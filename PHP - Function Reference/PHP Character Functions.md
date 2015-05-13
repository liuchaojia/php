# php字符函数
这个扩展提供的功能根据当前语言环境检查字符或字符串是否属于某个字符类。　　　　

当使用整数参数调用时, 这些函数的行为就像C从ctype.h中同行。

## 安装
从 PHP 4.2.0 版本开始，这些函数是默认启用的。 更早的版本，请使用 --enable-ctype 选项来配置和编译 PHP。 也可以使用 --disable-ctype 配置项来禁用 ctype 扩展。 

安装在内部的支持和安装PHP 4.3.0 ctype可用。
## 运行时配置
此扩展没有在 php.ini 中定义配置指令。

<table class="table table-bordered">
  <tr>
    <th width="35%" align="left" valign="top"> 函数             
    </th>
    <th width="60%" align="left" valign="top">描述</th>
    <th width="5%" align="left" valign="top">PHP</th>
  </tr>
<tr>
    <td valign="top"><a href="/php/php_function_ctype_alnum.htm">ctype_alnum()</a></td>
    <td valign="top">做字母和数字字符检测</td>
    <td valign="top">4.0.4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_ctype_alpha.htm">ctype_alpha()</a></td>
    <td valign="top">做纯字符检测</td>
    <td valign="top">4.0.4</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_ctype_cntrl.htm">ctype_cntrl()</a></td>
    <td valign="top">做控制字符检测</td>
    <td valign="top">4.0.4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_ctype_digit.htm">ctype_digit()</a></td>
    <td valign="top">做纯数字检测</td>
    <td valign="top">4.0.4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_ctype_graph.htm">ctype_graph()</a></td>
    <td valign="top">做可打印字符串检测，空格除外</td>
    <td valign="top">4.0.4</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_ctype_lower.htm">ctype_lower()</a></td>
    <td valign="top">做小写字符检测</td>
    <td valign="top">4.0.4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_ctype_print.htm">ctype_print()</a></td>
    <td valign="top">做可打印字符检测</td>
    <td valign="top">4.0.4</td>
  </tr> 
  <tr>
    <td valign="top"><a href="/php/php_function_ctype_punct.htm">ctype_punct()</a></td>
    <td valign="top">检测可打印的字符是不是不包含空白、数字和字母</td>
    <td valign="top">4.0.4</td>
  </tr>  
  <tr>
    <td valign="top"><a href="/php/php_function_ctype_space.htm">ctype_space()</a></td>
    <td valign="top">做空白字符检测</td>
    <td valign="top">4.0.4</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_ctype_upper.htm">ctype_upper()</a></td>
    <td valign="top">做大写字母检测</td>
    <td valign="top">4.0.4</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_ctype_xdigit.htm">ctype_xdigit()</a></td>
    <td valign="top">检测字符串是否只包含十六进制字符</td>
    <td valign="top">4.0.4</td>
  </tr>
</table>   
