# API描述
发送通知，v0.1.6开始加入。

## API地址
~~~
/api/v1/notice/media/${mediaId}/send
~~~
其中：
* `${mediaId}` - 媒介ID

## 请求方法
~~~
POST
~~~

## 请求参数
请求参数是一个完整的JSON：
~~~json
{
    "user": "...",
    "subject": "...",
    "body": "..."
}
~~~
其中：
* `user` - 接收人标识，每个媒介可能都有所不同
* `subject` - 通知标题
* `body` - 通知内容

## Curl调用示例
~~~bash
curl \
   -XPOST \
   -H"Content-type:application/json" \
   -d'{ "user":"LiBai", "subject":"hello", "body":"world" }' \
   "http://127.0.0.1:7777/api/v1/notice/media/J7vkHsyQKFtc7NTX/send?TeaKey=W7cy2eFpOKOPgOlaoDgbX11QNPAgIL5E"
~~~

## 返回结果示例
~~~json
{"ok":1}
~~~
