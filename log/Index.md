# 访问日志 
TeaWeb默认提供了相当完整的访问日志内容，可以在线浏览也可以通过MongoDB查看，还可以转发到别的存储媒介中。

## 日志存储策略
可以利用日志存储策略将访问日志输出到其他媒介中，比如文件、ElasticSearch、MySQL等等。

可以在[这里](Storage.md)查看详细的文档。

### 模板变量
* `${serverId}` - 代理服务ID
* `${backendId}` - 后端服务器ID
* `${backendAddress}` - 代理的后端的地址
* `${locationId}` - 路径规则ID
* `${fastcgiId}` - Fastcgi ID
* `${fastcgiAddress}` - Fastcgi后端地址
* `${rewriteId}` - 重写规则ID   
* `${teaVersion}` - TeaWeb版本
* `${remoteAddr}` - 终端地址
* `${remotePort}` - 终端端口
* `${remoteUser}` - 终端用户
* `${requestURI}` - 请求URI
* `${requestPath}` - 请求URL中的路径
* `${requestLength}` - 请求内容长度
* `${requestTime}` - 请求耗时
* `${requestMethod}` - 请求方法
* `${requestFilename}` - 请求的文件名
* `${scheme}` - 请求协议，http或者https
* `${proto}` - 带版本的请求协议，比如HTTP/1.0
* `${bytesSent}` - 响应的字节数（目前同`bodyBytesSent`）
* `${bodyBytesSent}` - 响应的字节数
* `${status}` - 响应的状态码
* `${statusMessage}` - 响应的信息
* `${sentHeader}` - 响应的头部信息
* `${timeISO8601}` - ISO 8601格式的本地时间，比如2018-07-16T23:52:24.839+08:00
* `${timeLocal}` - 本地时间，比如 17/Jul/2018:09:52:24 +0800
* `${msec}` - 带有毫秒的时间，比如 1531756823.054
* `${timestamp}` - unix时间戳，单位为秒     
* `${host}` - 主机名
* `${referer}` - 请求来源URL
* `${userAgent}` - 客户端信息
* `${request}` - 请求的简要说明，格式类似于 GET /hello/world HTTP/1.1
* `${contentType}` - 请求头部的Content-Type
* `${cookie.NAME}` - 某个cookie值
* `${queryString}` - 请求URI中的参数部分
* `${http.HEADER_NAME}` - 请求的头部信息，支持header_*和http_*，header_content_type, header_expires, http_content_type, http_user_agent
* `${header.HEADER_NAME}` - 请求的头部信息，同`${http.HEADER_NAME}`
* `${serverName}` - 接收请求的服务器名
* `${serverPort}` - 服务器端口
* `${serverProtocol}` - 服务器协议，类似于HTTP/1.0”   
* `${errors}` - 错误信息
* `${hasErrors}` - 是否包含有错误信息 
* `${log}` - 完整的访问日志信息，JSON格式   