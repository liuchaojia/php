# PHP Error 和 Logging 函数
这些都是处理错误处理和日志记录的函数。它们允许您定义自己的错误处理规则,以及可以修改错误记录的方式。这允许你改变和提高错误报告来满足您的需求。
　　　
使用这些日志记录功能,可以直接发送消息到其他机器电子邮件,系统日志,等等,所以你可以有选择地日志和监控您的应用程序和网站的最重要的部分。

## 安装
error 和 logging 函数是 PHP 核心的组成部分。无需安装即可使用这些函数。

## 运行时配置：
 这些函数的行为是在php . ini中设置的影响。这些设置定义如下


<table class="table table-bordered">
<tr><th>名称	</th><th>默认值	</th><th>可改变的	</th><th>变更日志</th></tr>
<tr><td>error_reporting</td><td>NULL</td><td>PHP_INI_ALL</td><td>&nbsp;</td></tr>
<tr><td>display_errors</td><td>"1"</td><td>PHP_INI_ALL</td><td>&nbsp;</td></tr>
<tr><td>display_startup_errors</td><td>"0"</td><td>PHP_INI_ALL</td><td>版本PHP 4.0.3之后可用
 
 
 

</td></tr>
<tr><td>log_errors</td><td>"0"</td><td>PHP_INI_ALL</td><td>&nbsp;</td></tr>
<tr><td>log_errors_max_len</td><td>"1024"</td><td>PHP_INI_ALL</td><td>版本PHP 4. 3.0之后可用</td></tr>
<tr><td>ignore_repeated_errors</td><td>"0"</td><td>PHP_INI_ALL</td><td>版本PHP 4. 3.0之后可用</td></tr>
<tr><td>ignore_repeated_source</td><td>"0"</td><td>PHP_INI_ALL</td><td>版本PHP 4. 3.0之后可用</td></tr>
<tr><td>report_memleaks</td><td>"1"</td><td>PHP_INI_ALL</td><td>版本PHP 4. 3.0之后可用</td></tr>
<tr><td>track_errors</td><td>"0"</td><td>PHP_INI_ALL</td><td>&nbsp;</td></tr>
<tr><td>html_errors</td><td>"1"</td><td>PHP_INI_ALL</td><td> 
PHP_INI_SYSTEM in PHP <= 4.2.3. 版本PHP 4. 0.2之后可用</td></tr>
<tr><td>docref_root</td><td>""</td><td>PHP_INI_ALL</td><td>版本PHP 4. 3.0之后可用</td></tr>
<tr><td>docref_ext</td><td>""</td><td>PHP_INI_ALL</td><td>版本PHP 4. 3.0之后可用</td></tr>
<tr><td>error_prepend_string</td><td>NULL</td><td>PHP_INI_ALL</td><td>&nbsp;</td></tr>
<tr><td>error_append_string</td><td>NULL</td><td>PHP_INI_ALL</td><td>&nbsp;</td></tr>
<tr><td>error_log</td><td>NULL</td><td>PHP_INI_ALL</td><td>&nbsp;</td></tr>
<tr><td>warn_plus_overloading</td><td>NULL</td><td>&nbsp;</td><td>版本PHP 4. 0.0不可用</td></tr>
</table>
## PHP Error 和 Logging 常数
PHP表明最早版本的PHP支持常数。您可以使用任何常数在php.ini文件配置中。

<table class="table table-bordered">
  <tr>
    <th width="5%" align="left">值	</th>
    <th width="35%" align="left">常量</th>

    <th width="55%" align="left">	描述</th>
    <th width="5%" align="left">PHP</th>
  </tr>
  <tr>
    <td valign="top">1</td>
    <td valign="top">E_ERROR</td>
    <td valign="top">致命的运行时错误。错误无法恢复。脚本的执行被中断。

</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">2</td>
    <td valign="top">E_WARNING</td>
    <td valign="top">非致命的运行时错误。脚本的执行不会中断。
</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">4</td>
    <td valign="top">E_PARSE</td>
    <td valign="top">编译时语法解析错误。解析错误只应该由解析器生成。
</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">8</td>
    <td valign="top">E_NOTICE</td>
    <td valign="top">运行时提示。可能是错误，也可能在正常运行脚本时发生。
</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">16</td>
    <td valign="top">E_CORE_ERROR</td>
    <td valign="top">由 PHP 内部生成的错误。
</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top">32</td>
    <td valign="top">E_CORE_WARNING</td>
    <td valign="top">由 PHP 内部生成的警告。
</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top">64</td>
    <td valign="top">E_COMPILE_ERROR</td>
    <td valign="top">由 Zend 脚本引擎内部生成的错误。
</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top">128</td>
    <td valign="top">E_COMPILE_WARNING</td>
    <td valign="top">由 Zend 脚本引擎内部生成的警告。
</td>

    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top">256</td>
    <td valign="top">E_USER_ERROR</td>
    <td valign="top">由于调用 trigger_error() 函数生成的运行时错误。
</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top">512</td>
    <td valign="top">E_USER_WARNING</td>
    <td valign="top">由于调用 trigger_error() 函数生成的运行时警告。
</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top">1024</td>
    <td valign="top">E_USER_NOTICE</td>
    <td valign="top">由于调用 trigger_error() 函数生成的运行时提示。
</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top">2048</td>
    <td valign="top">E_STRICT</td>
    <td valign="top">运行时提示。对增强代码的互用性和兼容性有益。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top">4096</td>
    <td valign="top">E_RECOVERABLE_ERROR</td>
    <td valign="top">可捕获的致命错误。（参阅 set_error_handler()）
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top">8191</td>
    <td valign="top">E_ALL</td>

    <td valign="top">所有的错误和警告，除了 E_STRICT。</td>
    <td valign="top">5</td>
  </tr>
</table>
## 函数列表
PHP：指示支持该常量的最早的 PHP 版本。

<table class="table table-bordered">
  <tr>
    <th width="40%" align="left" valign="top">函数	</th>
    <th width="55%" align="left" valign="top">说明</th>
    <th width="5%" align="left" valign="top">PHP</th>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_debug_backtrace.htm">debug_backtrace()</a></td>
    <td valign="top">生成 backtrace。
</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_debug_print_backtrace.htm">debug_print_backtrace()</a></td>
    <td valign="top">输出 backtrace。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_error_get_last.htm">error_get_last()</a></td>
    <td valign="top">获得最后发生的错误。</td>

    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_error_log.htm">error_log()</a></td>
    <td valign="top">向服务器错误记录、文件或远程目标发送一个错误。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_error_reporting.htm">error_reporting()</a></td>
    <td valign="top">
规定报告哪个错误。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_restore_error_handler.htm">restore_error_handler()</a></td>
    <td valign="top">恢复之前的错误处理程序。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_restore_exception_handler.htm">restore_exception_handler()</a></td>
    <td valign="top">恢复之前的异常处理程序。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_set_error_handler.htm">set_error_handler()</a></td>
    <td valign="top">设置用户自定义的错误处理函数。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_set_exception_handler.htm">set_exception_handler()</a></td>
    <td valign="top">设置用户自定义的异常处理函数。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top" height="26"><a href="/php/php_function_trigger_error.htm">trigger_error()</a></td>
    <td valign="top" height="26">
创建用户自定义的错误消息。/td>
    <td valign="top" height="26">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_user_error.htm">user_error()</a></td>
    <td valign="top">trigger_error() 的别名。</td>
    <td valign="top">4</td>
  </tr>
</table>   
