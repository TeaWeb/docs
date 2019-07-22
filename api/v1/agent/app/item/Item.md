# API描述
单个监控项信息，v0.1.6开始加入。

## API地址
~~~
/api/v1/agent/${agentId}/app/${appId}/item/${itemId}
~~~
其中：
* `${agentId}` - Agent ID
* `${appId}` - App ID
* `${itemId}` - 监控项ID

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
    "on": true,
    "id": "oVq0Nx7bYB7lwbrN",
    "name": "postgres",
    "sourceCode": "postgre.sql",
    "sourceOptions": {
      "addr": "127.0.0.1:5432",
      "dataFormat": 1,
      "databaseName": "postgres",
      "password": "123456",
      "sql": "SELECT * FROM settings",
      "timeoutSeconds": 10,
      "username": "postgres"
    },
    "interval": "30s",
    "thresholds": [],
    "charts": [],
    "recoverSuccesses": 1
  }
}
~~~