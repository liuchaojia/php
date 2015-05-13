## Apache 配置 PHP

Apache 使用httpd.conf 文件进行全局设置， .htaccess 文件对每个目录进行访问设置。老版本的 Apache 把httpd.conf 拆成三个文件 (access.conf、 httpd.conf，和 srm.conf），有些用户仍青睐于此。

Apache 服务器功能非常强大，但配置系统稍复杂。了解更多点击这里： www.apache.org
下一节讲述httpd.conf 的独特设置对 PHP直接影响。如果您默认安装， httpd.conf 会安装在以下位置 /etc/httpd/conf：
## Timeout

此设置的默认值设置为任何 HTTP 请求数秒后超时。如果设置 PHP大于此值，PHP 将保持原状，但用户可能会看到404 错误。在安全模式下，此值将被忽略；您必须在php.ini 文件中改用超时值
## DocumentRoot

DocumentRoot指定根目录为所有HTTP服务器进程。在Unix上它看起来像这样:

	DocumentRoot ./usr/local/apache_1.3.6/htdocs.

你可以选择任何文档作为根目录
## AddType
PHP MIME需要在这里设置要解析的 PHP 文件。请记住你可以关联PHP任何扩展文件像.php3、.php5 或.htm。

	AddType application/x-httpd-php .php
	AddType application/x-httpd-phps .phps
	AddType application/x-httpd-php3 .php3 .phtml
	AddType application/x-httpd-php .html


## Action

您必须取消注释Apache上的共享对象支持的Windows Apxs模块版本：

	LoadModule php4_module modules/php4apache.dll

或在 Unix 上的共享对象支持：

	LoadModule php4_module modules/mod_php.so

## AddModule

您必须取消注释Apache静态模块版本。

	AddModule mod_php4.c
