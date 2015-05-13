# 在Windows 用Apache安装PHP


在 Windows 上要用Apache安装PHP 5，请按照以下步骤操作。如果您的 PHP 和 Apache 版本不同，请下载相应的版本。

* 从www.apache.org/dist/httpd/binaries/win32 下载 Apache 服务器。你想要带有 no_src.msi 扩展名当前的稳定版本, 双击该安装程序文件进行安装 ；C:\Program files是一个常用的位置。安装程序还会问你是否要运行 Apache 作为一种服务器或从命令行或 DOS 提示符运行。我们建议您不要作为一种服务安装，因为这可能会导致启动问题。
* 使用您解压缩实用程序提取 PHP 二进制归档；到C:\PHP。
* 从您的 PHP 目录复制一些.dll 文件到您的系统目录 （C:\Windows）。php5ts.dll是一个常用文件。您可能还需要复制到 Apache 模块目录中和 Web 服务器模块-C:\PHP\Sapi\php5apache.dll中。很可能你也需要别的 dll 子文件夹-但开始只需要添加上面提到的两处,如果需要可添更多。
* 复制php.ini dist 或 php.ini 推荐 （最好是后者） 到您的 Windows 目录，并重新命名它为 php.ini。在文本编辑器 （例如记事本） 中打开此文件。编辑此文件，以获得配置指令 ；在他们的服务器上我们强烈建议新用户向 E_ALL 报告设置错误。
* 告诉您的 Apache 服务器要服务的文件和你想要什么的扩展名识别 PHP 文件（.php 是标准，但您可以使用.html、.phtml，或任何你想要的后缀名）。转到您的 HTTP 配置文件 （C:\Program Files\Apache Group\Apache\conf 或自定义路径），并使用文本编辑器打开 httpd.conf （这应该出现两次）搜索DocumentRoot 一词并将这两个路径更改为您想要提供的文件的目录。（默认值是 C:\Program Files\Apache Group\Apache\htdocs)。如下面第一行代码的所示，请添加至少一个 PHP 扩展指令：

	LoadModule php5_module modules/php5apache.dll
	AddType application/x-httpd-php .php .phtml

* 您可能还需要添加以下代码

	AddModule mod_php5.c

* 停止并重新启动 WWW 服务。去开始菜单-> 设置-> 控制面板-> 服务.向下滚动列表到 IIS Admin Service。选择并单击停止。停止后，选择万维网发布服务，单击开始。停止并重Internet 服务管理器还不够。由于这是 Windows系统，你也不妨重新启动。
* 打开一个文本编辑器。输入： <? php phpinfo () ；? >。将此文件在您的 Web 服务器的文档根目录中保存为 info.php。
* 启动任意 Web 浏览器并浏览这个文件. 为正确生成文件,必须始终使用 HTTP 请求 （http://www.testdomain.com/info.php 或 http://localhost/info.php 或 http://127.0.0.1/info.php），而不是文件名 （/ home/httpd/info.php) 。

你应该看到一段文字Congratulations, 恭喜你安装PHP成功!
