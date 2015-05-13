# 在 Linux/Unix 系统上面安装PHP

如果你计划在 Linux 或其他任何各种 Unix上安装 PHP，必须具备以下条件：


* PHP 资源分布http://www.php.net/downloads.php
* 最新Apache资源分布http://httpd.apache.org/download.cgi
* 支持 PHP运行的数据库，如果您打算用 （例如 MySQL，Oracle 等）。
* PHP 必须连接 （邮件服务器、BCMath 安装包，JDK，等等） 的任何其他支持的软件
* ANSI C 编码器
* Gnu make实用程序-您可以在这免费下载http://www.gnu.org/software/make
 
现在可以在您的 Linux 或 Unix 机器上安装 Apache 和 PHP5。如果您的 PHP 或者 Apache 版本有所不同的那么请做相应的调整。

* 如果你还没有这样做,解压你的Apache资源发布版。除非你有一个理由去做否则,/usr/local是标准的地方。

	gunzip -c apache_1.3.x.tar.gz

	tar -xvf apache_1.3.x.tar

* 如下构建Apache服务器

	cd apache_1.3.x

	./configure --prefix=/usr/local/apache --enable-so

	make

	make install

* 解压PHP源代码发布版。除非你有一个理由去做否则,/usr/local是标准的地方。
* 解压PHP源压缩包放到/usr/local下

	gunzip -c php-5.x.tar.gz
	tar -xvf php-5.x.tar
	cd php-5.x

* 假如你用的是MYSQL数据库，那么如下配置和搭建你的PHP

	./configure --with-apxs=/usr/sbin/apxs \

	            --with-mysql=/usr/bin/mysql
	make

	make install

* 安装 php.ini 文件。编辑此文件，以获得配置指令：

	cd ../../php-5.x

	cp php.ini-dist /usr/local/lib/php.ini

* 告诉你的 Apache 服务器文件在那里和如何辨别 PHP 的扩展名文件. php 是标准文件名，但可以使用.html、.phtml，或任何你想要使用的文件名。

	* 转到您的 HTTP 配置文件 （/usr/local/apache/conf或自定义路径）
	* 用文本编辑器打开 httpd.conf。
	* 搜索关键词DocumentRoof （DocumentRoof应该出现两次），并将两个路径更改为您想要服务文件的目录（例如/home/httpd）。我们建议一个主目录而不是默认的 /usr/local/apache/htdocs，因为它更安全，但它不必在主目录中。在此目录中，您将保存所有的 PHP 文件。
	
* 添加至少一个 PHP 扩展指令，如后面第一行代码所示。在第二行，我们已经添加了另一个的处理程序，解析所有 HTML 文件为 PHP 文件。

	AddType application/x-httpd-php .php

	AddType application/x-httpd-php .html

* 重启服务器，每次完成HTTP配置或者改变PHP.ini文件后都必须重启服务器。
 
	cd ../bin

	./apachectl start

* 将文档根目录权限设置为World-executable。目录中实际的 PHP 文件设置为World-readable(644)。如有必要，则替换/home/httpd为文档根目录，如下：

	chmod 755 /home/httpd/html/php

* 打开文本编辑器。类型：<?php phpinfo(); ?> 将此文件在Web 服务器的文档根目录中保存为 info.php。

* 启动任意一个Web 浏览器并浏览文件。你必须始终使用 HTTP 请求 （http://www.testdomain.com/info.php 或 http://localhost/info.php 或 http://127.0.0.1/info.php），而不是文件名 （/ home/httpd/info.php)以保证为正确解析文件。

您应该看到一个长方形的信息关于你的新的PHP安装消息Congratulations!。

