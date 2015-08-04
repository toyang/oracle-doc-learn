## oracle sequence可以使用的地方 ##
sequence的 `CURRVAL` 和 `NEXTVAL` 可以使用在下面所列的地方：

1. 可以使用在`SELECT`语句中，不能使用在`SELECT`语句的子查询中，下面示例将是错误的：
<pre>
select * from dept where exists(select seqtest.nextval from dual);--用在SELECT语句的子查询中
</pre>
2. 可以用在`INSERT`语句的子查询的select列表中

3. `INSERT`语句的`VALUES`中：
<pre>
insert into t values(seqtest.nextval,....)
</pre>
4. `UPDATE`语句的`SET`语句中