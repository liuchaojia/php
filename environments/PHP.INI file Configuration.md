# PHP.INI文件配置

PHP 配置文件php.ini，它是最终并且是最直接影响 PHP功能的组件。每次PHP初始化都要读取 php.ini 文件。换句话说，只要模块版本执行 CGI 版本或与每个脚本执行 CGI 版本，httpd都要重启。如果你的设置没有显示在phpinfo()中记得要停止并重新启动 httpd。如果它仍然无法显示，使用 phpinfo () 检查 php.ini 文件的路径。

配置文件被很好的注释和配置。键是区分大小写的，关键字的值则不区分大小写 ；忽略空白处和分号开头行。用1/0, Yes/No, On/off或true/false表示布尔值。在php.ini-Dist 文件中，默认值有助于PHP顺利安装，默认值可稍后调整。

在这里我们解释下 php.ini 文件重要设置，它需要PHP 解析器。

## Short_open_tag = Off

短标记看起来像这样： <? ?>。如果您想要使用 XML 功能,此选项必须设置关闭。
## safe_mode = Off

如果此设置为开时，你可能编译 PHP为--enable-safe-mode标志。安全模式与CGI 使用最相关。详见这一章前一部分"CGI compile-time options"一节。

## safe_mode_exec_dir = [DIR]

此选项只有在安全模式开启时才会生效；它也可以在 Unix 生成过程中与—with-exec--dir 标志一起设置。在安全模式下PHP只是执行此目录之外的外部二进制文件。默认值为 /usr/local/bin。这与提供正常的 PHP/HTML 网页页面无关。

## safe_mode_allowed_env_vars = [PHP_]
在安全模式下，用户设置此选项可以更改哪些环境变量，默认值是只为这些以"PHP_"前缀的变量。如果这项指令为空，则大多数变量都可变。
## safe_mode_protected_env_vars = [LD_LIBRARY_PATH]

在安全模式下，用户设置此选项可以更改哪些环境变量，即使允许更改设置safe_mode_allowed_env_vars。
## disable_functions = [function1, function2...]

出于安全考虑PHP4新增配置和PHP5标准配置中使用了禁用选定功能。以前，这需要PHP手动编辑成C 代码。文件系统、 系统和网络功能可能是第一选择，因为通过HTTP写入允许文件和更改系统永远不是安全的。

## max_execution_time = 30
此函数 set_time_limit() 不能在在安全模式下运行，所以这是安全模式下进行脚本超时的主要方式。在 Windows系统中，你必须中止消耗最大内存，而不是时间。如果您使用 Apache，也可以使用 Apache timeout设置超时，但这不适用站点上的非PHP文件。

## error_reporting = E_ALL & ~E_NOTICE
除了提示外包含所有的错误默认值是 E_ALL & ~ E_notice。开发服务器一定要最低限度设置成默认值；生产服务器可以考虑设置成较小的值。

## error_prepend_string = [""]
在书挡中，error_append_string，此设置允许将错误消息标记为与其他的文本不同的颜色，或者你想要的颜色。

## warn_plus_overloading = Off

如果在字符串中使用+运算符,作为表单中的值，这个设置会发出一条警告。
## variables_order = EGPCS

此配置设置将取代 gpc_order。现在都是随着register_globals被弃用。它设置不同变量的顺序：Environment, GET, POST, COOKIE, and SERVER (aka Built-in)。您或许可以更改此顺序。变量从左到右依次覆盖，而且，每次最右边那个优先级最高。这意味着如果你剩下默认设置，正巧使用相同名称的环境变量，POST 变量和COOKIE 变量，这样的话COOKIE 变量将会拥有该名称。其实，这不会经常发生的。

## register_globals = Off
此设置允许您决定是否注册EGPCS变量为全局变量。现在处于关闭状态，并且 PHP4.2，此标志默认设置是关闭的。现在都改用超全局变量数组。在这本书中所有列出的主要代码都使用的超全局变量数组。

## gpc_order = GPC
此设置GPC已弃用。

## magic_quotes_gpc = On
此设置转义引号传入GET/POST/COOKIE数据。如果你使用很多自动提交表单或其他形式提交并显示窗体值，您可能需要设置此指令开或准备使用addslashes() on string-type数据。

## magic_quotes_runtime = Off
此设置转义来自传入数据库和文本字符串的引号。当存储字符串和当返回值没有带斜杠时，请记住 SQL 添加斜杠在单引号和撇号前面。如果此设置为关，你又要输出SQL数据库中的字符串数据时请使用 stripslashes()。如果 magic_quotes_sybase 设置为 On，此必须处于关闭状态。
## magic_quotes_sybase = Off

这个参数只在启用magic_quotes_runtime时才有意义。如果启用了magic_quotes_sybase，所有来自外部资源的数据都将使用一个单引号而不是反斜线进行转义。如果数据来自Sybase数据库，这就非常有用，因为Sybase数据库的转义字符不是反斜线，而是非传统的单引号。
## auto-prepend-file = [path/to/file]

如果指定路径，每个 PHP 文件的开头必须自动include () 。包含路径设置适用。
## auto-append-file = [path/to/file]
If a path is specified here, PHP must automatically include() it at the end of 
如果指定路径，每个PHP文件的结尾必须自动include(). 除非你通过使用exit() 函数来避免。包含路径设置适用
## include_path = [DIR]

如果设置此值，你只要允许包含或需要这些目录中的文件即可。这些目录一般是你文档的根目录；如果在安全模式下运行，设置这些为强制执行。如此设置为包含您同一目录脚本中的文件。多个目录以冒号分隔：/usr/local/apache/htdocs:/usr/local/lib.
## doc_root = [DIR]

如果使用 Apache，你应该已经在 httpd.conf虚拟主机和此服务器设置了根目录。如果你使用安全模式或如果要在你站点部分启用 PHP，在此处设置此值（比如，仅在您网页根目录的一个子目录中）。
## file_uploads = [on/off]

如果使用 PHP 脚本上传文件则打开此标志。
## upload_tmp_dir = [DIR]

如果您明白HTTP 上传的具体影响，请注释这条！
## session.save-handler = files

除了在极少数情况下，请不要更改此设置。所以别管它。

## ignore_user_abort =  [On/Off]
设置客户端断开连接时是否中断脚本的执行 
PHP以命令行脚本执行时，当脚本终端结束，脚本不会被立即中止，除非设置 value 为 TRUE，否则脚本输出任意字符时会被中止。
此设置控制站点访问者点击关闭的原因。默认开启就意味着脚本持续运行到完成或超时。如果设置更改为关闭，该脚本将中止。此设置仅适用模块模式而不是CGI模式。
## mysql.default_host = hostname

如果不指定任何其他主机时，服务器主机默认使用最初连接到的数据库服务器的主机。
## mysql.default_user = username

如果未指定主机名，默认使用最初连接的服务器名。
## mysql.default_password = password

如果不指定设置密码则默认使用最初连接到的服务器密码。
