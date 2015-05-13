# 在Mac OS X安装PHP

Mac 用户可以二进制文件安装或源代码安装。事实上，你的 OS X 可能附带 Apache 和 PHP 预按装。这是可能是相当老的组件，它可能缺少许多不常见的扩展。

然而，如果你想要在您的便携式计算机上快速设置 Apache + PHP + MySQL/PostgreSQL，你只需要编辑你的 Apache 配置文件和打开 Web 服务器。
因此只需遵循以下步骤：

* 用文本编辑器打开Apache配置文件设为最高权限
 
	sudo open -a TextEdit /etc/httpd/httpd.conf
* 编辑文件，反注释以下行

	Load Module php5_module
	AddModule mod_php5.c
	AddType application/x-httpd-php .php

* 您可能还想要反注释 < Directory /home/*/Sites > 阻止或告诉 Apache 服务的目录。
* 重新启动 Web 服务器

	sudo apachectl graceful

* 打开文本编辑器。类型： <? php phpinfo () ；? >。将此文件保存在Web 服务器的根目录中并命名为 info.php。
* 启动Web 浏览器和浏览这个文件. 但为正确生成文件必须始终使用 HTTP 请求 （http://www.testdomain.com/info.php 或 http://localhost/info.php 或 http://127.0.0.1/info.php），而不是文件名 （/ home/httpd/info.php) 

您应该看到一个长方形的信息关于你的新的PHP安装消息Congratulations!
