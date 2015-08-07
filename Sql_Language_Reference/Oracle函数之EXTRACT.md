#### Oracle的`EXTRACT`函数 ####

<p>EXTRACT函数用于从日期中提取年，月，日，时，分，秒等，一般返回 <code>NUMBER</code>，其语法如下：</p>
![](../image/EXTRACT.png)

- 如果想获取 `YEAR` 或 `MONTH` ，EXPR的类型应该是`DATE`, `TIMESTAMP`, `TIMESTAMP WITH TIME ZONE`, `TIMESTAMP WITH LOCAL TIME ZONE`, 或 `INTERVAL YEAR TO MONTH`.

- 如果想获取 `DAY` ，EXPR的类型应该是 `DATE`,
`TIMESTAMP`, `TIMESTAMP WITH TIME ZONE`, `TIMESTAMP WITH LOCAL TIME ZONE`, 或 `INTERVAL DAY TO SECOND`。

- 如果想获取 `HOUR`, `MINUTE`, 或 `SECOND`，则EXPR应该是 `TIMESTAMP`, `TIMESTAMP WITH TIME ZONE`, `TIMESTAMP WITH LOCAL TIME ZONE`, 或 `INTERVAL DAY TO SECOND`。`DATE` 类型的参数是无效的，因为此函数会将 `DATE`类型当做 **ANSI** `DATE` 数据类型，它是没有时间字段的。
<pre>SELECT EXTRACT(hour FROM cast(t.current_date as timestamp)) "Month" FROM t1 t; --从DATE获得时间字段</pre>