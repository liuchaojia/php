# PHP Date / Time 函数
这些函数允许您从服务器获取日期和时间PHP脚本正在运行。您可以使用这些函数来在许多不同的方式格式化日期和时间。

## 安装
date/time 函数是 PHP 核心的组成部分。无需安装即可使用这些函数。
## Runtime 配置
这些函数的行为是在php . ini中设置的影响。所有这些参数都可以在PHP版本5和开始。
## Date/Time 配置选项：

<table class="table table-bordered">
  <tr>
    <th >
名称	</th>
    <th >默认值	</th>
    <th >描述	</th>
    <th >可改变</th>
  </tr>
  <tr>
    <td >date.default_latitude</td>
    <td >&nbsp;&quot;31.7667&quot;</td>
    <td >规定默认纬度（从 PHP 5 开始可用）。date_sunrise() 和 date_sunset() 使用该选项。




</td>
    <td >PHP_INI_ALL</td>
  </tr>
  <tr>
    <td >date.default_longitude</td>
    <td >&quot;35.2333&quot;</td>
    <td >规定默认经度（从 PHP 5 开始可用）。date_sunrise() 和 date_sunset() 使用该选项。
    </td>
    <td >PHP_INI_ALL</td>
  </tr>
  <tr>
    <td >date.sunrise_zenith</td>
    <td >&quot;90.83&quot;</td>
    <td >规定日出天顶（从 PHP 5 开始可用）。date_sunrise() 和 date_sunset() 使用该选项。</td>
    <td >PHP_INI_ALL</td>
  </tr>
  <tr>
    <td >date.sunset_zenith</td>
    <td >&quot;90.83&quot;</td>
    <td >规定日落天顶（从 PHP 5 开始可用）。date_sunrise() 和 date_sunset() 使用该选项。</td>
    <td >PHP_INI_ALL</td>
  </tr>
  <tr>
    <td >date.timezone</td>
    <td >&quot;&quot;</td>
    <td >规定默认时区（从 PHP 5.1 开始可用）。</td>
    <td >PHP_INI_ALL</td>
  </tr>

  </table>

PHP：指示支持该函数的最早的 PHP 版本。

<table class="table table-bordered">
<tr>
    <th width="38%" align="left" valign="top">
函数	
</th>
    <th width="57%" align="left" valign="top">描述</th>
    <th width="5%" align="left" valign="top">PHP</th>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_checkdate.htm">checkdate()</a></td>
    <td valign="top">验证格利高里日期。


</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_date_create.htm">date_create()</a></td>
    <td valign="top">返回new DateTime()对象</td>
    <td valign="top">5</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_date_date_set.htm">date_date_set()</a></td>
    <td valign="top">
设置日期</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_default_timezone_get.htm">date_default_timezone_get()</a></td>
    <td valign="top">返回默认时区。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_default_timezone_set.htm">date_default_timezone_set()</a></td>
    <td valign="top">设置默认时区。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_date_format.htm">date_format()</a></td>
    <td valign="top">返回根据指定格式进行格式化的日期。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_date_isodate_set.htm">date_isodate_set()</a></td>
    <td valign="top">设置 ISO 日期。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_date_modify.htm">date_modify()</a></td>
    <td valign="top">修改时间戳。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_date_offset_get.htm">date_offset_get()</a></td>
    <td valign="top">返回时区偏移。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_date_parse.htm">date_parse()</a></td>
    <td valign="top">返回一个带有指定日期的详细信息的关联数组。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_date_sun_info.htm">date_sun_info()</a></td>
    <td valign="top">返回一个包含有关指定日期与地点的日出/日落和黄昏开始/黄昏结束的信息的数组。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_sunrise.htm">date_sunrise()</a></td>
    <td valign="top">返回给定的日期与地点的日出时间。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_sunset.htm">date_sunset()</a></td>
    <td valign="top">返回给定的日期与地点的日落时间。
</td>
    <td valign="top">5</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_date_time_set.htm">date_time_set()</a></td>
    <td valign="top">设置时间。
</td>
    <td valign="top">5</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_date_timezone_get.htm">date_timezone_get()</a></td>
    <td valign="top">返回给定 DateTime 对象的时区。
</td>
    <td valign="top">5</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_date_timezone_set.htm">date_timezone_set()</a></td>
    <td valign="top">设置 DateTime 对象的时区。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_date.htm">date()</a></td>
    <td valign="top">格式化本地时间／日期。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_getdate.htm">getdate()</a></td>
    <td valign="top">返回日期／时间信息。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_gettimeofday.htm">gettimeofday()</a></td>
    <td valign="top">返回当前时间信息。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_gmdate.htm">gmdate()</a></td>
    <td valign="top">格式化 GMT/UTC 日期/时间。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_gmmktime.htm">gmmktime()</a></td>
    <td valign="top">取得 GMT 日期的 UNIX 时间戳。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_gmstrftime.htm">gmstrftime()</a></td>
    <td valign="top">Formats a GMT/UTC time/date according to locale settings</td>
    <td valign="top">3</td>根据本地区域设置格式化 GMT/UTC 时间／日期。

  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_idate.htm">idate()</a></td>
    <td valign="top">将本地时间/日期格式化为整数
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_localtime.htm">localtime()</a></td>
    <td valign="top">返回本地时间。
</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_microtime.htm">microtime()</a></td>
    <td valign="top">返回当前时间的微秒数。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_mktime.htm">mktime()</a></td>
    <td valign="top">返回一个日期的 Unix 时间戳。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_strftime.htm">strftime()</a></td>
    <td valign="top">根据区域设置格式化本地时间／日期。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_strptime.htm">strptime()</a></td>
    <td valign="top">解析由 strftime 生成的日期／时间。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_strtotime.htm">strtotime()</a></td>
    <td valign="top">将任何英文文本的日期或时间描述解析为 Unix 时间戳。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_time.htm">time()</a></td>
    <td valign="top">返回当前时间的 Unix 时间戳。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_timezone_abbreviations_list.htm">timezone_abbreviations_list()</a></td>
    <td valign="top">返回包含夏令时、偏移量和时区名称的关联数组。
</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_timezone_identifiers_list.htm">timezone_identifiers_list()</a></td>
    <td valign="top">返回带有所有时区标识符的数值数组。
</td>
    <td valign="top">5</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_timezone_name_from_abbr.htm">timezone_name_from_abbr()</a></td>
    <td valign="top">根据时区缩略语返回时区名称。
</td>
    <td valign="top">5</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_timezone_name_get.htm">timezone_name_get()</a></td>
    <td valign="top">返回时区的名称。
</td>
    <td valign="top">5</td>
  </tr>
   <tr>
    <td valign="top"><a href="/php/php_function_timezone_offset_get.htm">timezone_offset_get()</a></td>
    <td valign="top">返回相对于 GMT 的时区偏移。
</td>
    <td valign="top">5</td>
  </tr>
    <tr>
    <td valign="top"><a href="/php/php_function_timezone_open.htm">timezone_open()</a></td>
    <td valign="top">创建一个新的 DateTimeZone 对象。
</td>
    <td valign="top">5</td>
  </tr>
    <tr>
    <td valign="top"><a href="/php/php_function_timezone_transitions_get.htm">timezone_transitions_get()</a></td>
    <td valign="top">返回时区的所有转换。</td>
    <td valign="top">5</td>
  </tr>
  </table>

<h2>PHP Date / Time 常量</h2>
<table class="table table-bordered">
  <tr>
    <th width="40%" >常量</th>
    <th width="60%" >说明</th>
  </tr>
  <tr>
    <td >DATE_ATOM</td>
    <td >Atom (example: 2005-08-15T16:13:03+0000)</td>
  </tr>
  <tr>
    <td >DATE_COOKIE</td>
    <td >HTTP Cookies (example: Sun, 14 Aug 2005 16:13:03 UTC)</td>
  </tr>
<tr>
    <td >DATE_ISO8601</td>
    <td >ISO-8601 (example: 2005-08-14T16:13:03+0000)</td>
  </tr>
  <tr>
    <td >DATE_RFC822</td>
    <td >RFC 822 (example: Sun, 14 Aug 2005 16:13:03 UTC)</td>
  </tr>
  <tr>
    <td >DATE_RFC850</td>
    <td >RFC 850 (example: Sunday, 14-Aug-05 16:13:03 UTC)</td>
  </tr>
  <tr>
    <td >DATE_RFC1036</td>
    <td >RFC 1036 (example: Sunday, 14-Aug-05 16:13:03 UTC)</td>
  </tr>
  <tr>
    <td >DATE_RFC1123</td>
    <td >RFC 1123 (example: Sun, 14 Aug 2005 16:13:03 UTC)</td>
  </tr>
  <tr>
    <td >DATE_RFC2822</td>
    <td >RFC 2822 (Sun, 14 Aug 2005 16:13:03 +0000)</td>
  </tr>
  <tr>
    <td >DATE_RSS</td>
    <td >RSS (Sun, 14 Aug 2005 16:13:03 UTC)</td>
  </tr>
  <tr>
    <td >DATE_W3C</td>
    <td >World Wide Web Consortium (example: 
	2005-08-14T16:13:03+0000)</td>
  </tr>
  <tr>
    <td >SUNFUNCS_RET_TIMESTAMP</td>
    <td >Timestamp ( Available in 5.1.2 )</td>
  </tr>
  <tr>
    <td >SUNFUNCS_RET_STRING</td>
    <td >Hours:minutes (example: 08:02) ( Available in 5.1.2 )</td>
  </tr>
  <tr>
    <td >SUNFUNCS_RET_DOUBLE</td>
    <td >Hours as floating point number (example 8.75)( Available in 5.1.2 )</td>
  </tr>
</table>   

