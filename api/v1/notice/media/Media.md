# API描述
媒介信息，v0.1.6开始加入。

## API地址
~~~
/api/v1/notice/media/${mediaId}
~~~
其中：
* `${mediaId}` - 媒介信息

## 请求方法
~~~
GET
~~~

## 请求参数
无

## 返回结果示例
~~~json
{
  "config": {
    "id": "25AmaH8zi1lFBgAd",
    "on": true,
    "name": "脚本测试",
    "type": "script",
    "options": {
      "cwd": "",
      "env": null,
      "path": "",
      "script": "#!/usr/bin/env php\r\n\r\n\u003c?php\r\ntouch(\"/tmp/notice.\" . time() . \".php\");",
      "scriptLang": "php",
      "scriptType": "code"
    },
    "timeFrom": "00:00:00",
    "timeTo": "23:59:59",
    "rateMinutes": 1,
    "rateCount": 4
  }
}
~~~