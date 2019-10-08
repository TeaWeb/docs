# API描述
读取某个指标的统计数据。

## API地址
~~~
/api/v1/proxy/${serverId}/stat
~~~

其中：
* `${serverId}` - 代理服务ID

## 请求方法
~~~
GET
~~~

## 请求参数
* `item` - 指标代号，所有指标代号可以参考[数据指标](../../../../proxy/stat/Item.md)一节。
*  时间相关：
   * `year` - 年份，比如`2019`
   * `month` - 月份，由年份+月份组成，比如`201910`
   * `week` - 周，由年份+一年中第N周组成，比如`201940`，
   * `day` - 天，由年份+月份+日期组成，比如`20191004`
   * `hour` - 小时，由年份+月份+日期+小时组成，24小时制，比如`2019100416`
   * `minute` - 分钟，由年份+月份+日期+小时+分钟+秒组成，24小时制，比如`201910041622`
   * `second` - 秒，由年份+月份+日期+小时+分钟+秒组成，24小时制，比如`20191004162233`
* `params.参数名` - 指定参数值，每个指标可以使用的参数请参考[数据指标](../../../../proxy/stat/Item.md)一节
* `sort` - 排序值，每个指标的返回值请参考[数据指标](../../../../proxy/stat/Item.md)一节

以上所有的时间只需要提供其中一个即可，且可能需要加上前导0，比如日期是`6`的话，需要写成`06`。

示例API查询：
~~~
http://127.0.0.1:7777/api/v1/proxy/JnZ03pbDebcOQ7h9/stat?TeaKey=b5racVi8OsB1JG9fxfKOqxXWR033nTEg&item=browser.all.month&month=201910&sort=countReq&params.family=Chrome
~~~

## 返回结果示例
~~~json
[
  {
    "params": {
      "family": "Chrome",
      "major": "77"
    },
    "time": {
      "year": "2019",
      "month": "201910",
      "week": "201940",
      "day": "20191004",
      "hour": "2019100416",
      "minute": "201910041621",
      "second": "20191004162156"
    },
    "value": {
      "countIP": 0,
      "countPV": 0,
      "countReq": 4,
      "countUV": 0
    }
  },
  {
    "params": {
      "family": "Safari",
      "major": "13"
    },
    "time": {
      "year": "2019",
      "month": "201910",
      "week": "201940",
      "day": "20191004",
      "hour": "2019100416",
      "minute": "201910041622",
      "second": "20191004162233"
    },
    "value": {
      "countIP": 0,
      "countPV": 0,
      "countReq": 7,
      "countUV": 0
    }
  }
]
~~~
其中`params`为指标参数，`value`为统计数据。