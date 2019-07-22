# API描述
Agent列表，v0.1.6开始加入。

## API地址
~~~
/api/v1/agents
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
      "id": "Cgl8bj9b3puyA4LE",
      "on": false,
      "name": "web002",
      "host": "002",
      "key": "JoGY6EO8GCnQKOb5EfRMipSI6VGWCoMy",
      "allowAll": true,
      "allow": [],
      "apps": [
        {
          "id": "anWPJsir8M5C2grX",
          "on": true,
          "tasks": [
            {
              "id": "DzaTWdiriW1zmjsh",
              "on": true,
              "name": "echo Hello",
              "cwd": "",
              "env": [],
              "script": "#!/usr/bin/env bash\r\n\r\necho \"Hello\"\r\n",
              "isBooting": false,
              "schedule": [],
              "isManual": true,
              "version": 0
            }
          ],
          "items": [
            {
              "on": true,
              "id": "kLy5Q6oQr3foChSz",
              "name": "HTML Chart",
              "sourceCode": "script",
              "sourceOptions": {
                "cwd": "",
                "dataFormat": 1,
                "env": [],
                "path": "",
                "script": "#!/usr/bin/env bash\r\n\r\necho 1\r\n",
                "scriptLang": "shell",
                "scriptType": "code"
              },
              "interval": "30s",
              "thresholds": [],
              "charts": [
                {
                  "id": "OZMy7VqNPOeHWD2G",
                  "on": true,
                  "name": "HTML  Chart",
                  "description": "",
                  "columns": 1,
                  "type": "html",
                  "options": {
                    "html": "\u003cdiv\u003e\r\n    HTML\r\n\u003c/div\u003e"
                  },
                  "requirements": []
                }
              ],
              "recoverSuccesses": 1
            }
          ],
          "name": "Hello",
          "isSharedWithGroup": true,
          "sharedAgentIds": null,
          "noticeSetting": {
            "2": []
          }
        },
        {
          "id": "lZSHHLh34nbcfgn3",
          "on": true,
          "tasks": [],
          "items": [],
          "name": "bbb",
          "isSharedWithGroup": true,
          "sharedAgentIds": null,
          "noticeSetting": {}
        }
      ],
      "version": 29,
      "checkDisconnections": true,
      "countDisconnections": 0,
      "groupIds": [
        "2kMMzOcWWPFrhdaM"
      ],
      "autoUpdates": true,
      "appsIsInitialized": true,
      "noticeSetting": {
        "2": []
      }
    }
  },
  ...
]
~~~