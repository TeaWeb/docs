# API描述
读取系统状态，v0.1.6开始加入。

## API地址
~~~
/api/v1/status
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
  "arch": "amd64",
  "go": "go1.12.5",
  "heap": 106525744,
  "memory": 213225720,
  "database": true,
  "objects": 643558,
  "os": "darwin",
  "pid": 61388,
  "routines": 370,
  "version": "0.1.6"
}
~~~
其中 `database` 从 v0.1.7 开始加入。