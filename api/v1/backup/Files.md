# API描述
备份列表，v0.1.6开始加入。

## API地址
~~~
/api/v1/backup/files
~~~

## 请求方法
~~~
GET
~~~

## 请求参数
无

## 返回结果示例
~~~json
[
  {
    "isToday": true,
    "isYesterday": false,
    "name": "20190719.zip",
    "size": "0.67",
    "sizeBytes": 700530,
    "time": "2019-07-19 18:30:26"
  },
  {
    "isToday": false,
    "isYesterday": false,
    "name": "20190714.zip",
    "size": "0.65",
    "sizeBytes": 683512,
    "time": "2019-07-14 11:31:46"
  }
]
~~~