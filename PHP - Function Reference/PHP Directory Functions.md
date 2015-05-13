# PHP Directory 函数
这些函数提供操纵任何目录。
## 安装
Directory 函数是 PHP 核心的组成部分。无需安装即可使用这些函数。需要配置了PHP——enable-chroot-func选项来启用chroot()函数。
## 运行时配置：
此扩展没有在 php.ini 中定义配置指令。
## PHP Directory 常量
PHP：指示支持该常量的最早的 PHP 版本。

<table class="table table-bordered">
  <tr>
    <th width="38%" align="left">常量</th>
    <th width="57%" align="left">说明</th>
    <th width="5%" align="left">PHP</th>
  </tr>
  <tr>
    <td valign="top">DIRECTORY_SEPARATOR</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top">PATH_SEPARATOR</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">4</td>
  </tr>
</table>
<h2>函数列表</h2>
<p><b>PHP</b>: PHP：指示支持该函数的最早的 PHP 版本。 </p>
<table class="src" cellpadding="5" border="1" width="100%">
  <tr>
    <th width="35%" align="left" valign="top">函数</th>
    <th width="60%" align="left" valign="top">说明</th>
    <th width="5%" align="left" valign="top">PHP</th>
  </tr>
<tr>
    <td valign="top"><a href="/php/php_function_chdir.htm">chdir()</a></td>
    <td valign="top">改变当前的目录。






</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_chroot.htm">chroot()</a></td>
    <td valign="top">改变当前进程的根目录。</td>
    <td valign="top">4.0.4</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_dir.htm">dir()</a></td>
    <td valign="top">打开一个目录句柄，并返回一个对象。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_closedir.htm">closedir()</a></td>
    <td valign="top">关闭目录句柄。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_getcwd.htm">getcwd()</a></td>
    <td valign="top">返回当前目录。</p>
    <td valign="top">4</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_opendir.htm">opendir()</a></td>
    <td valign="top">
打开目录句柄。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_readdir.htm">readdir()</a></td>
    <td valign="top">返回目录句柄中的条目。</td>
    <td valign="top">4</td>
  </tr> 
  <tr>
    <td valign="top"><a href="/php/php_function_rewinddir.htm">rewinddir()</a></td>
    <td valign="top">重置目录句柄。</td>
    <td valign="top">4</td>
  </tr>  
  <tr>
    <td valign="top"><a href="/php/php_function_scandir.htm">scandir()</a></td>
    <td valign="top">
列出指定路径中的文件和目录。</td>
    <td valign="top">5</td>
  </tr>
</table>

注意:与文件系统相关的更多的函数,检查File System Functions
