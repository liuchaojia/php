# PHP Filesystem 函数
文件系统函数是PHP提供您所有的拿到样品功能用来访问和操作文件系统当你可能需要操作一个文件时。
## 安装
Filesystem 函数是 PHP 核心的组成部分。无需安装即可使用这些函数。
## Runtime 配置
文件系统函数的行为受到 php.ini 中设置的影响。


<table class="table table-bordered">
<tr><th>名称	</th><th>默认	</th><th>可改变</th><th>	更改日志</th></tr>
<tr><td>allow_url_fopen</td><td>"1"</td><td>PHP_INI_ALL</td><td>用PHP PHP_INI_ALL < = 4.3.4。用PHP PHP_INI_SYSTEM < 6。由于PHP 4.0.4可用。
</td></tr>
<tr><td>allow_url_include</td><td>"0"</td><td>PHP_INI_ALL</td><td>PHP_INI_SYSTEM  PHP 5。从PHP 5.2.0可用。</td></tr>
<tr><td>user_agent</td><td>NULL</td><td>PHP_INI_ALL</td><td>PHP 4.3.0 版以后可用。</td></tr>
<tr><td>default_socket_timeout</td><td>"60"</td><td>PHP_INI_ALL</td><td>PHP 4.3.0 版以后可用。</td></tr>
<tr><td>from</td><td>""</td><td>PHP_INI_ALL</td><td>&nbsp;</td></tr>
<tr><td>auto_detect_line_endings</td><td>"0"</td><td>PHP_INI_ALL</td><td>PHP 4.3.0 版以后可用。</td></tr>
</table>
## Unix / Windows 兼容性
当在 Unix 平台上规定路径时，正斜杠 (/) 用作目录分隔符。而在 Windows 平台上，正斜杠 (/) 和反斜杠 (\) 均可使用。
## PHP Filesystem 常量

PHP表明最早版本的PHP支持常数。您可以使用任何常数在php.ini文件配置中。

<table class="table table-bordered">
  <tr>
    <th width="35%" align="left">常量</th>
    <th width="55%" align="left">说明</th>
    <th width="5%" align="left">PHP</th>
  </tr>
  <tr>
    <td valign="top">GLOB_BRACE</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">GLOB_ONLYDIR  </td>
    <td valign="top">&nbsp;</td>
    <td valign="top">&nbsp;</td>
  </tr>
    <tr>
    <td valign="top">GLOB_MARK</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
   <td valign="top">GLOB_NOSORT </td>
    <td valign="top">&nbsp;</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
   <td valign="top">GLOB_NOCHECK</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
   <td valign="top">GLOB_NOESCAPE</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
   <td valign="top">PATHINFO_DIRNAME</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">&nbsp;</td>
  </tr>
    <tr>
   <td valign="top">PATHINFO_BASENAME</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">&nbsp;</td>
  </tr>
   <tr>
   <td valign="top">PATHINFO_EXTENSION</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">&nbsp;</td>
  </tr>
<tr>
   <td valign="top">PATHINFO_FILENAME  </td>
    <td valign="top">&nbsp;</td>
    <td valign="top">5.2.0</td>
  </tr>
  <tr>
   <td valign="top">FILE_USE_INCLUDE_PATH</td>
    <td valign="top">Search for filename in include_path</td>
    <td valign="top">5.0.0</td>
  </tr>
   <tr>
   <td valign="top">FILE_APPEND</td>
    <td valign="top">Append content to existing file.</td>
    <td valign="top">&nbsp;</td>
  </tr>
    <tr>
   <td valign="top">FILE_IGNORE_NEW_LINES  </td>
    <td valign="top">Strip EOL characters</td>
    <td valign="top">5.0.0</td>
  </tr>
    <tr>
   <td valign="top">FILE_SKIP_EMPTY_LINES</td>
    <td valign="top">Skip empty lines</td>
    <td valign="top">5.0.0</td>
  </tr>
     <tr>
   <td valign="top">FILE_BINARY  </td>
    <td valign="top">Binary mode</td>
    <td valign="top">6.0.0</td>
  </tr>
      <tr>
   <td valign="top">FILE_TEXT </td>
    <td valign="top">Text mode</td>
    <td valign="top">6.0.0</td>
  </tr>
  </table>
## PHP Filesystem 函数
PHP：指示支持该函数的最早的 PHP 版本。


<table class="table table-bordered">
  <tr>
    <th width="40%" align="left" valign="top">函数	</th>
    <th width="55%" align="left" valign="top">说明</th>
    <th width="5%" align="left" valign="top">PHP</th>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_basename.htm">basename()</a></td>
    <td valign="top">返回路径中的文件名部分。

</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_chgrp.htm">chgrp()</a></td>
    <td valign="top">改变文件组。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_chmod.htm">chmod()</a></td>
    <td valign="top">改变文件模式。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_chown.htm">chown()</a></td>
    <td valign="top">改变文件所有者。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_clearstatcache.htm">clearstatcache()</a></td>
    <td valign="top">清除文件状态缓存。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_copy.htm">copy()</a></td>
    <td valign="top">复制文件。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_delete.htm">delete()</a></td>
    <td valign="top">删除文件</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_dirname.htm">dirname()</a></td>
    <td valign="top">返回路径中的目录名称部分。






</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_disk_free_space.htm">disk_free_space()</a></td>
    <td valign="top">返回目录的可用空间。</td>
    <td valign="top">4.0.7</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_disk_total_space.htm">disk_total_space()</a></td>
    <td valign="top">
返回一个目录的磁盘总容量。</td>
    <td valign="top">4.0.7</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_diskfreespace.htm">diskfreespace()</a></td>
    <td valign="top">
disk_free_space() 的别名。</td>
    <td valign="top">4.0.7</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_fclose.htm">fclose()</a></td>
    <td valign="top">关闭打开的文件。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_feof.htm">feof()</a></td>
    <td valign="top">测试文件指针是否到了文件结束的位置。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_fflush.htm">fflush()</a></td>
    <td valign="top">向打开的文件输出缓冲内容。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_fgetc.htm">fgetc()</a></td>
    <td valign="top">从打开的文件中返回字符。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_fgetcsv.htm">fgetcsv()</a></td>
    <td valign="top">从打开的文件中解析一行，校验 CSV 字段。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_fgets.htm">fgets()</a></td>
    <td valign="top">
从打开的文件中返回一行。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_fgetss.htm">fgetss()</a></td>
    <td valign="top">从打开的文件中读取一行并过滤掉 HTML 和 PHP 标记。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_file_exists.htm">file_exists()</a></td>
    <td valign="top">检查文件或目录是否存在。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_file_get_contents.htm">file_get_contents()</a></td>
    <td valign="top">将文件读入字符串。
</td>
    <td valign="top">4.3.0</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_file_put_contents.htm">file_put_contents()</a></td>
    <td valign="top">将字符串写入文件。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_file.htm">file()</a></td>
    <td valign="top">file() 函数把整个文件读入一个数组中。
    </td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_fileatime.htm">fileatime()</a></td>
    <td valign="top">返回文件的上次访问时间。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_filectime.htm">filectime()</a></td>
    <td valign="top">返回文件的上次改变时间。
</td>
    <td valign="top">3</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_filegroup.htm">filegroup()</a></td>
    <td valign="top">返回文件的组 ID。
</td>
    <td valign="top">3</td>
  </tr>
  </table>