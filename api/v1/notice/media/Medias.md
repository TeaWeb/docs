# API描述
媒介列表，v0.1.6开始加入。

## API地址
~~~
/api/v1/notice/medias
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
  },
  {
    "config": {
      "id": "j0a8NFoBKguRoowI",
      "on": true,
      "name": "Shell脚本",
      "type": "script",
      "options": {
        "cwd": "",
        "env": null,
        "path": "",
        "script": "#!/usr/bin/env php\r\n\r\n\u003c?php\r\nfile_put_contents(\"/tmp/notice.\" . date(\"H_i_s\") . \".php\", $_ENV[\"NoticeUser\"] . \" \" . $_ENV[\"NoticeSubject\"] . \"\\n\" . $_ENV[\"NoticeBody\"]);",
        "scriptLang": "php",
        "scriptType": "code"
      },
      "timeFrom": "00:00:00",
      "timeTo": "23:59:59",
      "rateMinutes": 1,
      "rateCount": 1
    }
  },
  {
    "config": {
      "id": "A06IzHOA55BzJG4R",
      "on": true,
      "name": "微信企业",
      "type": "webhook",
      "options": {
        "body": "",
        "contentType": "params",
        "headers": null,
        "method": "POST",
        "params": null,
        "url": "http://127.0.0.1:9991/webhook?user=${NoticeUser}"
      },
      "timeFrom": "00:00:00",
      "timeTo": "23:59:59",
      "rateMinutes": 1,
      "rateCount": 1
    }
  }
]
~~~