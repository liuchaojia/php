## 用IIS在Windows上安装PHP

Windows 服务器安装PHP在IIS上运行比Unix 上简单得多，因为这涉及到一个预编译的二进制文件，而不是源码生成。

如果你打算在 Windows 上安装 PHP，以下是必备条件：

* 支持PHP运行的 Web 服务器。在老版本PHP 中, IIS/PWS 是最简单的选择，因为 PHP 模块是可用的 ；但是 PHP 现在增添了更为广泛的模块窗口。
* 正确安装支持PHP的数据库像 MySQL 或 Oracle 等 （如果您计划使用一个）
* PHP Windows 二进制发行版 （下载地址:www.php.net/ downloads.php)
* 一个实用解压缩程序文件 （PC 文件压缩实用程序搜索 http://download.cnet.com)

按照以下步骤在您的 Windows 计算机上安装 Apache 和 PHP5。如果您的 PHP 版本合适请下载相应版本。

* 使用解压缩实用程序提取二进制归档；C:\PHP 是一个通常位置。
* 复制PHP 目录的.dll 文件到您的系统目录 （通常位置 C:\Winnt\System32)。php5ts.dll是一个常用文件。可能还需要复制对应的 Web 服务器模块 位置为: -C:\PHP\Sapi\php5isapi.dll 。很可能你也需要别的 dll 子文件夹-但开始只需要添加上面提到的两处,如果需要可添更多。
* 复制php.ini dist 或 php.ini 推荐 （最好是后者） 到您的 Windows 目录 （C:\Winnt 或 C:\Winnt40），并将其重命名为 php.ini。在文本编辑器 （例如记事本） 中打开此文件。编辑此文件，以获得配置指令 ；在他们的服务器上我们强烈建议新用户向 E_ALL 报告设置错误。现在，最重要的事情是确保doc_root 指令的路径和目录匹配IIS Inetpub 文件夹 （或你想服务于那里）。
* 停止并重新启动 WWW 服务。去开始菜单-> 设置-> 控制面板-> 服务.向下滚动列表到 IIS Admin 服务。选择并单击停止。停止后，选择万维网发布服务，单击开始。停止并重新启动服务从在 Internet 服务管理器中是不够的。由于这是 Windows，你也不妨重新启动。
* 打开一个文本编辑器。输入： <? php phpinfo () ；? >。将此文件在您的 Web 服务器文档的根目录中保存为 info.php。
* 启动任一Web 浏览器和浏览此文件, 为正确生成文件, 必须始终使用 HTTP 请求 （http://www.testdomain.com/info.php 或 http://localhost/info.php 或 http://127.0.0.1/info.php），而不是文件名 （/ home/httpd/info.php) 。

你应该看到一段文字Congratulations, 恭喜你安装PHP成功!
	
