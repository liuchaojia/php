# PHP Array 函数

这些函数允许您以各种方式进行交互和操作数组。数组是必不可少的存储、管理和操作的变量集。
## 安装：

array 函数是 PHP 核心的组成部分。无需安装即可使用这些函数。

## 运行时配置

该扩展模块在PHP.INI中未定义任何设置指令。
## PHP Array 常量

<table class="table table-bordered">
  <tr>
    <th width="35%" align="left">常量	          </th>
    <th width="60%" align="left">描述</th>
  </tr>
  <tr>
    <td valign="top">CASE_LOWER</td>
    <td valign="top">CASE_LOWER	用在 array_change_key_case() 中将数组键名转换成小写字母。	
    </td>
  </tr>
  <tr>
    <td valign="top">CASE_UPPER</td>
    <td valign="top">用在 array_change_key_case() 中将数组键名转换成大写字母。	</td>
  </tr>
	<tr>
    <td valign="top">SORT_ASC</td>
    <td valign="top">用在 array_multisort() 函数中，使其升序排列。</td>
  </tr>
  <tr>
    <td valign="top">SORT_DESC</td>
    <td valign="top">用在 array_multisort() 函数中，使其降序排列。</td>
  </tr>
  <tr>
    <td valign="top">SORT_REGULAR</td>
    <td valign="top">用于对对象进行通常比较。	</td>
  </tr>
  <tr>
    <td valign="top">SORT_NUMERIC</td>
    <td valign="top">用于对对象进行数值比较。	</td>
  </tr>
  <tr>
    <td valign="top">SORT_STRING</td>
    <td valign="top">用于对对象进行字符串比较。	</td>
  </tr>
  <tr>
    <td valign="top">SORT_LOCALE_STRING</td>
    <td valign="top">基于当前区域来对对象进行字符串比较。</td>
  </tr>
  <tr>
    <td valign="top">COUNT_NORMAL</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">COUNT_RECURSIVE</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">EXTR_OVERWRITE</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">EXTR_SKIP</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">EXTR_PREFIX_SAME</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">EXTR_PREFIX_ALL</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">EXTR_PREFIX_INVALID</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">EXTR_PREFIX_IF_EXISTS</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">EXTR_IF_EXISTS</td>
    <td valign="top">&nbsp;</td>
  </tr>
  <tr>
    <td valign="top">EXTR_REFS</td>
    <td valign="top">&nbsp;</td>
  </tr>
</table>	

## PHP Array 函数




<table class="table table-bordered">
  <tr>
    <th width="35%" align="left" valign="top">函数</th>
    <th width="60%" align="left" valign="top">描述</th>
    <th width="5%" align="left" valign="top">PHP</th>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array.htm">array()</a></td>
    <td valign="top">创建数组。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_change_key_case.htm">array_change_key_case()</a></td>
    <td valign="top">返回其键均为大写或小写的数组。

    </td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_chunk.htm">array_chunk()</a></td>
    <td valign="top">把一个数组分割为新的数组块。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_combine.htm">array_combine()</a></td>
    <td valign="top">通过合并两个数组来创建一个新数组。

    </td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_count_values.htm">array_count_values()</a></td>
    <td valign="top">用于统计数组中所有值出现的次数。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_diff.htm">array_diff()</a></td>
    <td valign="top">返回两个数组的差集数组。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_diff_assoc.htm">array_diff_assoc()</a></td>
    <td valign="top">比较键名和键值，并返回两个数组的差集数组。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_diff_key.htm">array_diff_key()</a></td>
    <td valign="top">比较键名，并返回两个数组的差集数组。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_diff_uassoc.htm">array_diff_uassoc()</a></td>
    <td valign="top"通过用户提供的回调函数做索引检查来计算数组的差集。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_diff_ukey.htm">array_diff_ukey()</a></td>
    <td valign="top">用回调函数对键名比较计算数组的差集。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_fills.htm">array_fill()</a></td>
    <td valign="top">用给定的值填充数组。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_fill_keys.htm">array_fill_keys()</a></td>
    <td valign="top">Fill an array with values, specifying keys</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_filter.htm">array_filter()</a></td>
    <td valign="top">array_filter()
     用回调函数过滤数组中的元素。
    </td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_flip.htm">array_flip()</a></td>
    <td valign="top">交换数组中的键和值。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_intersect.htm">array_intersect()</a></td>
    <td valign="top">计算数组的交集。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_intersect_assoc.htm">array_intersect_assoc()</a></td>
    <td valign="top">比较键名和键值，并返回两个数组的交集数组。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_intersect_key.htm">array_intersect_key()</a></td>
    <td valign="top">使用键名比较计算数组的交集。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_intersect_uassoc.htm">array_intersect_uassoc()</a></td>
    <td valign="top">带索引检查计算数组的交集，用回调函数比较索引。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_intersect_ukey.htm">array_intersect_ukey()</a></td>
    <td valign="top">用回调函数比较键名来计算数组的交集。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_key_exists.htm">array_key_exists()</a></td>
    <td valign="top">检查给定的键名或索引是否存在于数组中。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_keys.htm">array_keys()</a></td>
    <td valign="top">返回数组中所有的键名。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_map.htm">array_map()</a></td>
    <td valign="top">将回调函数作用到给定数组的单元上。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_merge.htm">array_merge()</a></td>
    <td valign="top">把一个或多个数组合并为一个数组。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_merge_recursive.htm">array_merge_recursive()</a></td>
    <td valign="top">递归地合并一个或多个数组。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_multisort.htm">array_multisort()</a></td>
    <td valign="top">对多个数组或多维数组进行排序。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_pad.htm">array_pad()</a></td>
    <td valign="top">用值将数组填补到指定长度。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_pop.htm">array_pop()</a></td>
    <td valign="top">将数组最后一个单元弹出（出栈）。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_product.htm">array_product()</a></td>
    <td valign="top">计算数组中所有值的乘积。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_push.htm">array_push()</a></td>
    <td valign="top">array_push()
将一个或多个单元（元素）压入数组的末尾（入栈）。
    </td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_rand.htm">array_rand()</a></td>
    <td valign="top">从数组中随机选出一个或多个元素，并返回。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_reduce.htm">array_reduce()</a></td>
    <td valign="top">用回调函数迭代地将数组简化为单一的值。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_reverse.htm">array_reverse()</a></td>
    <td valign="top">将原数组中的元素顺序翻转，创建新的数组并返回。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_search.htm">array_search()</a></td>
    <td valign="top">在数组中搜索给定的值，如果成功则返回相应的键名。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_shift.htm">array_shift()</a></td>
    <td valign="top">删除数组中的第一个元素，并返回被删除元素的值。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_slice.htm">array_slice()</a></td>
    <td valign="top">在数组中根据条件取出一段值，并返回。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_splice.htm">array_splice()</a></td>
    <td valign="top">把数组中的一部分去掉并用其它值取代。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_sum.htm">array_sum()</a></td>
    <td valign="top">计算数组中所有值的和。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_udiff.htm">array_udiff()</a></td>
    <td valign="top">array_rand()
     回调函数比较数据来计算数组的差集。
    </td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_udiff_assoc.htm">array_udiff_assoc()</a></td>
    <td valign="top">带索引检查计算数组的差集，用回调函数比较数据。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_udiff_uassoc.htm">array_udiff_uassoc()</a></td>
    <td valign="top">带索引检查计算数组的差集，用回调函数比较数据和索引。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_uintersect.htm">array_uintersect()</a></td>
    <td valign="top">计算数组的交集，用回调函数比较数据。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_uintersect_assoc.htm">array_uintersect_assoc()</a></td>
    <td valign="top">带索引检查计算数组的交集，用回调函数比较数据。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_uintersect_uassoc.htm">array_uintersect_uassoc()</a></td>
    <td valign="top">带索引检查计算数组的交集，用回调函数比较数据和索引。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_unique.htm">array_unique()</a></td>
    <td valign="top">删除数组中重复的值。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_unshift.htm">array_unshift()</a></td>
    <td valign="top">在数组开头插入一个或多个元素。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_values.htm">array_values()</a></td>
    <td valign="top">返回数组中所有的值。
    </td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_walk.htm">array_walk()</a></td>
    <td valign="top">
    对数组中的每个成员应用用户函数。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_array_walk_recursive.htm">array_walk_recursive()</a></td>
    <td valign="top">对数组中的每个成员递归地应用用户函数。</td>
    <td valign="top">5</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_arsort.htm">arsort()</a></td>
    <td valign="top">对数组进行逆向排序并保持索引关系。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_asort.htm">asort()</a></td>
    <td valign="top">对数组进行排序并保持索引关系。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_compact.htm">compact()</a></td>
    <td valign="top">建立一个数组，包括变量名和它们的值。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_count.htm">count()</a></td>
    <td valign="top">计算数组中的元素数目或对象中的属性个数。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_current.htm">current()</a></td>
    <td valign="top">返回数组中的当前元素。

    </td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_each.htm">each()</a></td>
    <td valign="top">返回数组中当前的键／值对并将数组指针向前移动一步。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_end.htm">end()</a></td>
    <td valign="top">将数组的内部指针指向最后一个元素。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_extract.htm">extract()</a></td>
    <td valign="top">从数组中将变量导入到当前的符号表。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_in_array.htm">in_array()</a></td>
    <td valign="top">检查数组中是否存在指定的值。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_key.htm">key()</a></td>
    <td valign="top">从关联数组中取得键名。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_krsort.htm">krsort()</a></td>
    对数组按照键名逆向排序。
ksort()
。
list()

natcasesort()

natsort()

next()

pos()

prev()

range()

</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_ksort.htm">ksort()</a></td>
    <td valign="top">对数组按照键名排序.</td>
    <td valign="top">3</td>
  </tr>.
  <tr>
    <td valign="top"><a href="/php/php_function_list.htm">list()</a></td>
    <td valign="top">把数组中的值赋给一些变量。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_natcasesort.htm">natcasesort()</a></td>
    <td valign="top">用“自然排序”算法对数组进行不区分大小写字母的排序。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_natsort.htm">natsort()</a></td>
    <td valign="top">用“自然排序”算法对数组排序。</td>
    <td valign="top">4</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_next.htm">next()</a></td>
    <td valign="top">将数组中的内部指针向前移动一位。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_pos.htm">pos()</a></td>
    <td valign="top">current() 的别名。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_prev.htm">prev()</a></td>
    <td valign="top">将数组的内部指针倒回一位。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_range.htm">range()</a></td>
    <td valign="top">建立一个包含指定范围的元素的数组。
    </td> 
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_reset.htm">reset()</a></td>
    <td valign="top">将数组的内部指针指向第一个元素。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_rsort.htm">rsort()</a></td>
    <td valign="top">对数组逆向排序。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_shuffle.htm">shuffle()</a></td>
    <td valign="top">把数组中的元素按随机顺序重新排列。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_sizeof.htm">sizeof()</a></td>
    <td valign="top">count() 的别名。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_sort.htm">sort()</a></td>
    <td valign="top">对数组排序。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_uasort.htm">uasort()</a></td>
    <td valign="top">使用用户自定义的比较函数对数组中的值进行排序并保持索引关联。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_uksort.htm">uksort()</a></td>
    <td valign="top">使用用户自定义的比较函数对数组中的键名进行排序。</td>
    <td valign="top">3</td>
  </tr>
  <tr>
    <td valign="top"><a href="/php/php_function_usort.htm">usort()</a></td>
    <td valign="top">使用用户自定义的比较函数对数组中的值进行排序。</td>
    <td valign="top">3</td>
  </tr>
  </table>   

