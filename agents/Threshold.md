# 阈值
我们在[创建监控项](http://teaos.cn/doc/agents/Item.md#4%E6%B7%BB%E5%8A%A0%E9%98%88%E5%80%BC)时已经使用了阈值。阈值用于我们判断获取的数值是否满足了某个触发条件。

## 变量
### 内置变量
监控项选择数据源后，就可以使用数据源提供的一些变量。比如对于`负载（Load）`数据源，提供的的变量有`${load1}`、`${load5}`、`${load15}`。可以在界面中查看这些变量及说明。

### 索引
如果获取的数据是一个数组的话，可以通过索引获取某个索引上的值，索引从`0`开始，比如：
~~~json
[1, 2.5, 3, 4.7, 5]
~~~
则：
* `${0}`表示第一个数据：`1`
* `${1}`表示第二个数据：`2.5`
* `${2}`的值为：`3`
* 以此类推

如果返回的数据是单行数据，则只支持`${0}`，比如：
~~~json
"123"
~~~
则 `${0}` 的值为 `123`。

索引也支持级联，对于：
~~~json
[
	{ "name": "ZHANG" },
	{ "name": "LI" },
	{ "name": "WANG" }
]
~~~
则：
* `${0.name}`值为`ZHANG`
* `${1.name}`值为`LI`
* `${2.name}`值为`WANG`

### $符号
从v0.0.10开始，可以使用一个单独的`$`来表示数组中的每一个元素，比如对于：
~~~json
[
	{
		"name": "ZHANG SAN",
		"count": 10
	},
	{
		"name": "LI SI",
   		"count": 15
    },
    {
    	"name": "WANG ER",
       	"count": 20
    }
]
~~~
则： 
* `${$.count}` 表示数组中任意一个元素中的`count`值，如果用于阈值判断，则自动会循环当前数组，有一个元素满足条件即返回。

`$`符号不一定在最前面，也可以在中间，以下都是合法的：
* `${$}` - 每一个元素
* `${$.count}` - 每一个元素中的`count`值
* `${user.books.$.price}` - `user.books`的每一个元素中的`price`值

### ROW变量
从v0.1.1开始，可以在通知消息中使用`${ROW.xxx}`变量来表示使用`$`匹配的变量，比如对于上面的JSON数据，可以设置通知消息为：
~~~
发现${ROW.name}有异常
~~~

又比如，对于硬盘分区数据：
~~~json
{
  "partitions": [
    {
      "free": 533154402304,
      "inodesFree": 9223372036854776000,
      "inodesPercent": 1.0842021724855044e-17,
      "inodesTotal": 9223372036854776000,
      "inodesUsed": 1,
      "name": "/private/var/vm",
      "percent": 0.20099320386597236,
      "total": 998921388032,
      "used": 1073762304
    },
    {
      "free": 533154402304,
      "inodesFree": 9223372036851067000,
      "inodesPercent": 4.021000112736095e-11,
      "inodesTotal": 9223372036854776000,
      "inodesUsed": 3708718,
      "name": "/",
      "percent": 46.52807144146622,
      "total": 998921388032,
      "used": 463919046656
    }
  ]
}
~~~
如果设置阈值为`${partitions.$.percent} gt 80`，则：
* `${ROW.name}` - 匹配的分区数据的`name`值
* `${ROW.used}` - 匹配的分区数据的已使用字节数
* 依次类推...

通知消息可以设置为：
~~~
${ROW.name}已使用80%
~~~
这样通知消息发出时，`${ROW.name}`就会被替换成相对应的分区名。

### 命名变量
如果获取的数据是一个键值对结构的话，可以通过命名获取某个键对应的值，比如：
~~~json
{
	"name": "ZHANG SAN",
	"age": 18,
	"books": [ "Java", "Golang", "Python" ]
}
~~~
则：
* `${name}`表示`name`对应的值：`ZHANG SAN`
* `${age}`表示`age`对应的值：`18`
* `${books}`表示`books`对应的值 `[ "Java", "Golang", "Python" ]`
* `${books.0}`值为`Java`，`${books.1}`值为`Golang`，`${books.2}`表示`Python`

### OLD变量
从 v0.0.10 开始起支持`${OLD}`变量，表示当前监控项获取的上一条数据，比如有两条记录：
当前数据：
~~~json
{
	"load1": 3.2
}
~~~

上一条数据：
~~~json
{
	"load1": 4.5
}
~~~
那么 `${load1} - ${OLD.load1}` 的值为 `-1.3`。

如果没有上一条记录，则`${OLD}`值和当前数据值一致。

`${OLD}`的一个很大的用处是用来检测数据变化，从而发出通知或者执行其他操作。

## Agent主机相关变量
从v0.1.1开始，Agent主机相关阈值的通知消息中可以使用一组内置的变量：
* `${AGENT.name}` - Agent主机名
* `${AGENT.host}` - Agent主机地址
* `${APP.name}` - App名称
* `${ITEM.name}` - 监控项名称

## 运算符
参数值支持加(+)、减(-)、乘(*)、除(/)、取余(%)等运算符，如果有这些运算符的时候，参数值支持`Javascript`语法，对于：
~~~json
{
	"load1": 3.2,
	"load5": 2.5,
	"load15": 4
}
~~~
则：
* `${load1} / 10` 值为 `0.32`
* `${load1} * ${load15}` 值为 `12.8`
* `Math.abs(${load1} - 4)` 值为 `0.8`，其中我们使用了`Javascript`的内置方法`Math.abs()`

## Javascript
从v0.0.10开始，除了在参数值中包含一些运算符自动激活`Javascript`语法外，还可以直接使用`javascript:表达式`来表示当前表达式使用了`Javascript`语法，比如：
~~~javascript
javascript:new Date().getTime() / 1000 - ${timestamp}
~~~
例子中的`${timestamp}`从数值中获取。

## 格式化
可以使用函数来格式化阈值：
~~~
值 | 函数1(参数1, 参数2, ...) | 函数2 | ...
~~~
如上所示，使用竖线`|`分隔多个函数，如果函数有参数的话，可以使用`(`和`)`来包含，多个参数之间用英文逗号`,`隔开。

目前支持的函数有：

### 转换为浮点数数字 - float
v0.1.8.2加入，没有参数，或者参数为格式化字符串，随后跟更多格式化中的参数：
~~~
${ROW.percent | float}                         => 123.456712
${ROW.percent | float('%.2f')}                 => "123.46"
${ROW.percent | float('%.2f%s', ' Percent')}   => "123.46 Percent"
~~~

### 对数字四舍五入 - round
v0.1.8.2加入，没有参数或者参数为需要保留的小数点个数：
~~~
${ROW.percent | round}     => "123"
${ROW.percent | round(2)}  => "123.46"
~~~

### 对数字进行取不小于它的整数 - ceil
v0.1.8.2加入：
~~~
${ROW.percent | ceil}      => "124"
~~~

### 对数字进行取不大于它的整数 - floor
v0.1.8.2加入：
~~~
${ROW.percent | floor}    => "123"
~~~

### 格式化 - format
v0.1.8.2加入，参数为格式化字符串，随后跟更多格式化中的参数：
~~~
${ROW.percent | format('%.2f')}                   => "123.46"
${ROW.percent | format('%.2f%s', ' Percent')}     => "123.46 Percent"
~~~

### 附加参数 - append
v0.1.8.2加入，参数为格式化字符串，随后跟更多格式化中的参数：
~~~
${ROW.name | append('Book')}           => GolangBook
${ROW.name | append('A', 'B', 'C')}    => GolangABC
~~~
