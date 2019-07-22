# API描述
查看任务信息，v0.1.6开始加入。

## API地址
~~~
/api/v1/agent/${agentId}/app/${appId}/task/${taskId}
~~~
其中：
* `${agentId}` - Agent ID
* `${appId}` - App ID
* `${taskId}` - 任务ID

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
    "id": "YiQRg9tMm1npi2Nf",
    "on": true,
    "name": "echo",
    "cwd": "",
    "env": [],
    "script": "#!/usr/bin/env bash\r\n\r\necho `date`",
    "isBooting": false,
    "schedule": [],
    "isManual": true,
    "version": 1
  }
}
~~~