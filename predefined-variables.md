# PHP预定义变量

PHP提供了大量预定义的变量来它运行的脚本。PHP提供了一套附加的预定数组，这些数组变量包含了来自 web 服务器（如果可用），运行环境，和用户输入的数据。这些新的数组被称为超全局变量:

以下所有的变量在全局范围内自动生效：

PHP超全局变量：


<table class="table table-bordered">
<tr>
<th width="10%">变量</th><th width="90%">说明</th>
</tr>
<tr>
<td>$GLOBALS</td>
<td>包含一个引用变量这就表示其在脚本的所有作用域中都是可用的，变量的名字就是数组的键。
</td>
</tr>
<tr>
<td>$_SERVER</td>
<td>是一个包含了诸如头信息(header)、路径(path)、以及脚本位置(script locations)等等信息的数组。这个数组中的项目由 Web 服务器创建。不能保证每个服务器都提供全部项目；见下一节的完整列表的所有服务器变量。</td>
</tr>
<tr>
<td>$_GET</td>
<td>通过HTTP GET方法传递给当前脚本的变量的关联数组。</td>
</tr>
<tr>
<td>$_POST</td>
<td>通过HTTP POST方法传递给当前脚本的变量的关联数组。</td>
</tr>
<tr>
<td>$_FILES</td>
<td>通过 HTTP POST 方式上传到当前脚本的项目的数组。</td>
</tr>
<tr>
<td>$_REQUEST</td>
<td> 一个关联数组包含了 $_GET，$_POST 和 $_COOKIE 的数组。</td>
</tr>
<tr>
<td>$_COOKIE</td>
<td>通过 HTTP Cookies 方式传递给当前脚本的变量的关联数组。</td>
</tr>
<tr>
<td>$_SESSION</td>
<td>通过会话方式使用于当前脚本的变量的关联数组。</td>
</tr>
<tr>
<td>$_PHP_SELF</td>
<td>包含一个PHP脚本的文件名的字符串。</td>
</tr>
<tr>
<td>$php_errormsg</td>
<td>是一个包含文本的最后一个PHP生成的错误消息的变量。</td>
</tr>
</table>


服务器变量:$ _SERVER

$_SERVER 是一个包含了诸如头信息(header)、路径(path)、以及脚本位置(script locations)等等信息的数组。这个数组中的项目由 Web 服务器创建。不能保证每个服务器都提供全部项目。


<table class="table table-bordered">
<tr>
<th width="10%">变量</th><th width="90%">说明</th>
</tr>
<tr>
<td>$_SERVER['PHP_SELF']</td>
<td>
当前执行脚本的文件名，与 document root 有关。

</td>
</tr>
<tr>
<td>$_SERVER['argv']</td>
<td> 传递给该脚本的参数的数组。当脚本以命令行方式运行时，argv 变量传递给程序 C 语言样式的命令行参数。当通过 GET 方式调用时，该变量包含查询字符串。</td>
</tr>
<tr>
<td>$_SERVER['argc']</td>
<td>包含命令行模式下传递给该脚本的参数的数目(如果运行在命令行模式下)。 </td>
</tr>
<tr>
<td>$_SERVER['GATEWAY_INTERFACE']</td>
<td>服务器使用的 CGI 规范的版本；例如，“CGI/1.1”。</td>
</tr>
<tr>
<td>$_SERVER['SERVER_ADDR']</td>
<td> 当前运行脚本所在的服务器的 IP 地址。 </td>
</tr>
<tr>
<td>$_SERVER['SERVER_NAME']</td>
<td> 当前运行脚本所在的服务器的主机名。如果脚本运行于虚拟主机中，该名称是由那个虚拟主机所设置的值决定。</td>
</tr>
<tr>
<td>$_SERVER['SERVER_SOFTWARE']</td>
<td 服务器标识字符串，在响应请求时的头信息中给出。 </td>
</tr>
<tr>
<td>
$_SERVER['SERVER_PROTOCOL']
</td>
<td> 请求页面时通信协议的名称和版本。例如，“HTTP/1.0”。 </td>
</tr>
<tr>
<td>$_SERVER['REQUEST_METHOD']</td>
<td>访问页面使用的请求方法；例如，“GET”, “HEAD”，“POST”，“PUT”。 </td>
</tr>
<tr>
<td>$_SERVER['REQUEST_TIME']</td>
<td>请求开始时的时间戳。从 PHP 5.1.0 起可用。 </td>
</tr>
<tr>
<td>$_SERVER['QUERY_STRING']</td>
<td>query string（查询字符串），如果有的话，通过它进行页面访问。</td>
</tr>
<tr>
<td>$_SERVER['DOCUMENT_ROOT']</td>
<td>当前运行脚本所在的文档根目录。在服务器配置文件中定义。 </td>
</tr>
<tr>
<td>$_SERVER['HTTP_ACCEPT']</td>
<td>当前请求头中 Accept: 项的内容，如果存在的话。 </td>
</tr>
<tr>
<td>$_SERVER['HTTP_ACCEPT_CHARSET']</td>
<td>当前请求头中 Accept-Charset: 项的内容，如果存在的话。例如：“iso-8859-1,*,utf-8”。 </td>
</tr>
<tr>
<td>$_SERVER['HTTP_ACCEPT_ENCODING']</td>
<td>当前请求头中 Accept-Encoding: 项的内容，如果存在的话。例如：“gzip”。 </td>
</tr>
<tr>
<td>$_SERVER['HTTP_ACCEPT_LANGUAGE']</td>
<td> 当前请求头中 Accept-Language: 项的内容，如果存在的话。例如：“en”。 </td>
</tr>
<tr>
<td>$_SERVER['HTTP_CONNECTION']</td>
<td>当前请求头中 Connection: 项的内容，如果存在的话。例如：“Keep-Alive”。 </td>
</tr>
<tr>
<td>$_SERVER['HTTP_HOST']</td>
<td>  当前请求头中 Host: 项的内容，如果存在的话。 </td>
</tr>
<tr>
<td>$_SERVER['HTTP_REFERER']</td>
<td>页面的地址(如果有的话),将当前页面的用户代理。 </td>
</tr>
<tr>
<td>$_SERVER['HTTP_USER_AGENT']</td>
<td> 该字符串表明了访问该页面的用户代理的信息。一个典型的例子是：Mozilla/4.5 [en] (X11; U; Linux 2.2.9 i586)。 </td>
</tr>
<tr>
<td>$_SERVER['HTTPS']</td>
<td>如果脚本是通过 HTTPS 协议被访问，则被设为一个非空的值。 </td>
</tr>
<tr>
<td>$_SERVER['REMOTE_ADDR']</td>
<td>浏览当前页面的用户的 IP 地址。 </td>
</tr>
<tr>
<td>$_SERVER['REMOTE_HOST']</td>
<td>浏览当前页面的用户的主机名。DNS 反向解析不依赖于用户的 REMOTE_ADDR。 </td>
</tr>
<tr>
<td>
$_SERVER['REMOTE_PORT']
</td>
<td>服务器机器上的端口使用的web服务器进行通信。为默认设置,这将是“80”。 </td>
</tr>
<tr>
<td>$_SERVER['SCRIPT_FILENAME']</td>
<td> 当前执行脚本的绝对路径。</td>
</tr>
<tr>
<td>$_SERVER['SERVER_ADMIN']</td>
<td>该值指明了 Apache 服务器配置文件中的 SERVER_ADMIN 参数。如果脚本运行在一个虚拟主机上，则该值是那个虚拟主机的值。 </td>
</tr>
<tr>
<td>$_SERVER['SERVER_PORT']</td>
<td>Web 服务器使用的端口。默认值为 “80”。如果使用 SSL 安全连接，则这个值为用户设置的 HTTP 端口。 </td>
</tr>
<tr>
<td>$_SERVER['SERVER_SIGNATURE']</td>
<td>包含了服务器版本和虚拟主机名的字符串。 
</td>
</tr>
<tr>
<td>$_SERVER['PATH_TRANSLATED']</td>
<td> 当前脚本所在文件系统（非文档根目录）的基本路径。这是在服务器进行虚拟到真实路径的映像后的结果。</td>
</tr>
<tr>
<td>$_SERVER['SCRIPT_NAME']</td>
<td> 包含当前脚本的路径。这是有用的页面需要指向自己。</td>
</tr>
<tr>
<td>$_SERVER['REQUEST_URI']</td>
<td>
给定的URI来访问这个页面;例如,/ index . html。 </td>
</tr>
<tr>
<td>$_SERVER['PHP_AUTH_DIGEST']</td>
<td>当运行在Apache模块做消化HTTP身份验证这个变量设置为发送的“授权”头端。</td>
</tr>
<tr>
<td>$_SERVER['PHP_AUTH_USER']</td>
<td>运行在Apache和IIS(ISAPI PHP 5)作为HTTP身份验证模块做这个变量设置为用户提供的用户名。</td>
</tr>
<tr>
<td>$_SERVER['PHP_AUTH_PW']</td>
<td> 当运行在Apache和IIS(ISAPI PHP 5)作为HTTP身份验证模块做这个变量设置为用户提供的密码。</td>
</tr>
<tr>
<td>$_SERVER['AUTH_TYPE']</td>
<td>当运行在Apache HTTP身份验证模块做这个变量设置为身份验证类型。</td>
</tr>
</table>
