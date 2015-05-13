# PHP Calendar 函数

日历的扩展提供了一系列的功能函数来简化不同的日历格式之间的转换。 

中介或标准是基于儒略日计数。儒略日计数的计数天从1月1日开始,公元前4713年日历系统之间的转换,您必须首先转换为儒略日计数, 然后再转换为日历格式。

## 安装
就不得不通过 --enable-calendar 编译 PHP，这样日历函数才能工作。 
## 运行时配置
该扩展模块在PHP.INI中未定义任何设置指令。
## PHP Calendar 常量

<table class="table table-bordered">
  <tr>
    <th width="35%" align="left">常量</th>
    <th width="60%" align="left">说明</th>
    <th width="5%" align="left">PHP</th>

  </tr>
  <tr>
    <td valign="top">CAL_GREGORIAN</td>
    <td valign="top">公历

</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top">CAL_JULIAN</td>

    <td valign="top">罗马儒略历
    </td>
    <td valign="top">3</td>
  </tr>
	<tr>
    <td valign="top">CAL_JEWISH</td>
    <td valign="top">犹太历
    </td>
    <td valign="top">3</td>

  </tr>
  <tr>
    <td valign="top">CAL_FRENCH</td>

    <td valign="top">法国共和历</td>
    <td valign="top">3</td>
  </tr>
  <tr>

    <td valign="top">CAL_NUM_CALS</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top">CAL_DOW_DAYNO</td>
    <td valign="top">&nbsp;</td>

    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top">CAL_DOW_SHORT</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">3</td>
  </tr>

  <tr>
    <td valign="top">CAL_DOW_LONG</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top">CAL_MONTH_GREGORIAN_SHORT</td>

    <td valign="top">&nbsp;</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top">CAL_MONTH_GREGORIAN_LONG</td>

    <td valign="top">&nbsp;</td>
    <td valign="top">3</td>

  </tr>
  <tr>
    <td valign="top">CAL_MONTH_JULIAN_SHORT</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top">CAL_MONTH_JULIAN_LONG</td>

    <td valign="top">&nbsp;</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top">CAL_MONTH_JEWISH</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">3</td>

  </tr>
  <tr>
    <td valign="top">CAL_MONTH_FRENCH</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top">CAL_EASTER_DEFAULT</td>

    <td valign="top">&nbsp;</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top">CAL_EASTER_DEFAULT</td>

    <td valign="top">&nbsp;</td>
    <td valign="top">4</td>

  </tr>
  <tr>
    <td valign="top">CAL_EASTER_ROMAN</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top">CAL_EASTER_ALWAYS_GREGORIAN</td>

    <td valign="top">&nbsp;</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top">CAL_EASTER_ALWAYS_JULIAN</td>

    <td valign="top">&nbsp;</td>
    <td valign="top">4</td>

  </tr>
  <tr>
    <td valign="top">CAL_JEWISH_ADD_ALAFIM_GERESH</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top">CAL_JEWISH_ADD_ALAFIM</td>

    <td valign="top">&nbsp;</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top">CAL_JEWISH_ADD_GERESHAYIM</td>
    <td valign="top">&nbsp;</td>
    <td valign="top">5</td>

  </tr>
</table>
## PHP Calendar 函数
PHP：指示支持该函数的最早的 PHP 版本。

<table class="table table-bordered">
  <tr>
    <th width="35%" align="left" valign="top">函数</th>
    <th width="60%" align="left" valign="top">说明</th>
    <th width="5%" align="left" valign="top">PHP</th>
  </tr>
<tr>
    <td valign="top"><a href="/php/php_function_cal_days_in_month.htm">cal_days_in_month()</a></td>
    <td valign="top">针对指定的年份和日历，返回一个月中的天数。



</td>
    <td valign="top">4</td>
  </tr>

  <tr>
    <td valign="top"><a href="/php/php_function_cal_from_jd.htm">cal_from_jd()</a></td>
    <td valign="top">把儒略日计数转换为指定日历的日期。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_cal_info.htm">cal_info()</a></td>

    <td valign="top">返回有关给定日历的信息。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_cal_to_jd.htm">cal_to_jd()</a></td>
    <td valign="top">
     把日期转换为儒略日计数。</td>
    <td valign="top">4</td>

  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_easter_date.htm">easter_date()</a></td>
    <td valign="top">
     返回指定年份的复活节午夜的 Unix 时间戳。</td>
    <td valign="top">3</td>
  </tr>
  <tr>

    <td valign="top"><a href="/php/php_function_easter_days.htm">easter_days()</a></td>
    <td valign="top">返回指定年份的复活节与 3 月 21 日之间的天数。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_frenchtojd.htm">FrenchToJD()</a></td>
    <td valign="top">
将法国共和历法转换成为儒略日计数。</td>

    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_gregoriantojd.htm">GregorianToJD()</a></td>
    <td valign="top">
将格利高里历法转换成为儒略日计数。
</td>
    <td valign="top">3</td>
  </tr>

  <tr>
    <td valign="top"><a href="/php/php_function_jddayofweek.htm">JDDayOfWeek()</a></td>
    <td valign="top">返回日期在周几。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_jdmonthname.htm">JDMonthName()</a></td>

    <td valign="top">返回月的名称。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_jdtofrench.htm">JDToFrench()</a></td>
    <td valign="top">把儒略日计数转换为法国共和国历法。
</td>
    <td valign="top">3</td>

  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_jdtogregorian.htm">JDToGregorian()</a></td>
    <td valign="top">把儒略日计数转换为格利高里历法。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>

    <td valign="top"><a href="/php/php_function_jdtojewish.htm">jdtojewish()</a></td>
    <td valign="top">把儒略日计数转换为犹太历法。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_jdtojulian.htm">JDToJulian()</a></td>
    <td valign="top">把儒略日计数转换为儒略历。
</td>

    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_jdtounix.htm">jdtounix()</a></td>
    <td valign="top">把儒略日计数转换为 Unix 时间戳。
</td>
    <td valign="top">4</td>
  </tr>

  <tr>
    <td valign="top"><a href="/php/php_function_jewishtojd.htm">JewishToJD()</a></td>
    <td valign="top">把犹太历法转换为儒略日计数。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_juliantojd.htm">JulianToJD()</a></td>

    <td valign="top">把儒略历转换为儒略日计数。
</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_unixtojd.htm">unixtojd()</a></td>
    <td valign="top">把 Unix 时间戳转换为儒略日计数。</td>
    <td valign="top">4</td>

  </tr>
</table>   

