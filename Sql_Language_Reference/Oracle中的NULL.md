#### Oracle中的NULL ####

&ensp;&ensp;&ensp;&ensp;
什么是NULL？如果一列没有值，我们就叫这列为NULL，或者说包含NULL。使用NULL来表示一个值是未知的或这个值是无意义的。Oracle也将一个长度为0的字符视为NULL。

> 尽管Oracle现在将长度为0的字符视为NULL，但不代表未来的版本中也会这么做。所以Oracle建议不要将长度为0的字符串视为和NULL一样。

- `NULL`值的比较：

&ensp;&ensp;&ensp;&ensp;
只能使用 `IS NULL` 和 `IS NOT NULL`来比较 `NULL` 值。如果你使用其他比较方式，那么返回的结果是 `UNKNOWN`(`a==NULL` 结果 `UNKNOWN`) 。NULL值和任何其他的值或NULL本身都不相等。然而，当使用 `DECODE` 函数时，Oracle认为两个NULL值是相等的。
当NULL做为复合主键时，Oracle也认为两个NULL值是相等的。

- `NULL`在条件语句中

&ensp;&ensp;&ensp;&ensp;
一个条件语句如果计算为 `UNKNOWN` 的话，它差不多相当于 `FALSE`。例如，在一个 `SELECT` 语句中，如果 `WHERE` 条件语句计算结果是 `UNKNOWN` 的话，这个语句返回0行。然而计算结果是 `UNKNOWN` 和 `FALSE`并不相同，因为 `NOT FALSE` 计算结果是 `TRUE` ，但 `NOT UNKNOWN` 的计算结果还是 `UNKNOWN`。