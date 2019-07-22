# API描述
执行任务，v0.1.6开始加入。

## API地址
~~~
/api/v1/agent/${agentId}/app/${appId}/task/${taskId}/run
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
{"ok":1}
~~~