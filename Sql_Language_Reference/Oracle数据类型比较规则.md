#### Oracle不同数据类型的比较规则 ####



*  日期类型比较规则

&ensp;&ensp;&ensp;&ensp;
日期类型的比较规则是：后来的日期总是大于先前的日期，比如“2015-3-12”大于“2015-2-12”

* 字符类型的比较规则

&ensp;&ensp;&ensp;&ensp;分为两种尺度:
    
    


1. 二进制顺序或语言顺序

2. 填充空格式或非填充空格式

&ensp;&ensp;&ensp;&ensp;**二进制顺序**或**基于语言的顺序**。二进制比较是指比较两个字符的字符集中对应的数字编码，这是默认的比较规则。

> oracle认为空白字符小于其他非空白字符。


&ensp;&ensp;&ensp;&ensp;填充空格式是指如果两个字符串如果长度不相等，则较短的字符串会使用空格填充直到和较长的长度一致。oracle仅对两个都是CHAR, NCHAR类型的字符使用这种比较规则；非填充空格式比较则是比较双方至少有一个是varchar2或nvarchar2.