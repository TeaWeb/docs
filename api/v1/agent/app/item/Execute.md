# API描述
执行监控项，v0.1.6开始加入。

## API地址
~~~
/api/v1/agent/${agentId}/item/app/${appId}/${itemId}/execute
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
{"ok":1}
~~~