## oracle sequence可以使用的地方 ##
#### sequence的 `CURRVAL` 和 `NEXTVAL` 可以使用在下列地方： ####


-  可以使用在`SELECT`语句中，不能使用在`SELECT`语句的子查询中，下面示例将是错误的：
<pre>
select * from dept where exists(select seqtest.nextval from dual);--用在SELECT语句的子查询中
</pre>

-  可以用在`INSERT`语句的子查询的select列表中


-  `INSERT`语句的`VALUES`中：
<pre>
insert into t values(seqtest.nextval,....)
</pre>

-  `UPDATE`语句的`SET`语句中

#### sequence的 `CURRVAL` 和 `NEXTVAL` 不可以使用在下列地方： ####

- `DELETE`,`SELECT`,`UPDATE`语句的子查询中

- 视图的查询中

- 带有`DISTINCT`操作符的`SELECT`语句

- 带有`GROUP BY`和`ORDER BY`子句的`SELECT`语句

- 带有集合操作符（`UNION`,`INTERSECT`,`MINUS`）的`SELECT`语句

- `SELECT`语句的`WHERE`子句中

- `ALTER TABLE`和`CREATE TABLE`语句的列的默认值（`DEFAULT`）

- `CHECK`约束的条件中

#### sequence使用例子： ####

- `SELECT employees_seq.nextval FROM DUAL;`    *--查询序列的下一个值*

- `INSERT INTO employees VALUES (employees_seq.nextval, 'John', 'Doe', 'jdoe', '555-1212');`*--使用在insert语句中*
