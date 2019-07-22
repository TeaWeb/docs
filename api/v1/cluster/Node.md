# API描述
节点信息，v0.1.6开始加入。

## API地址
~~~
/api/v1/cluster/node
~~~

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
    "id": "7MLNcm73rZqB8Ael",
    "on": false,
    "name": "主节点",
    "clusterId": "UuQPCSLiynigaHen",
    "clusterSecret": "2nfGgAeWv84u0rYU3ZtAam1wekHvBIcM",
    "clusterAddr": "127.0.0.1:7781",
    "role": "MASTER"
  },
  "isActive": false,
  "isChanged": false
}
~~~