# API描述
下载某个备份文件，v0.1.6开始加入。

## API地址
~~~
/api/v1/backup/file/:filename
~~~
其中：
* `${filename}` - 文件名

## 请求方法
~~~
GET
~~~

## 请求参数
无

## 返回结果示例
返回一个zip文件内容。