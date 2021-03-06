# FAQ
## TeaWeb是干吗用的？
`TeaWeb` 是一个Web反向代理的服务工具，类似于Nginx、LVS之类，只不过 `TeaWeb` 试图提供一个可视化的界面，让用户操作特别简单，同时也自动实现日志、监控、统计等功能。

## 我能使用TeaWeb代替nginx吗？
`nginx`是一个非常优秀的Web Server，如果你在大规模地在用，不建议轻易更换。如果正在小规模使用，`TeaWeb`也提供了`nginx`具有的基础Web代理功能，既可以分发静态文件，可以分发Fastcgi请求，也实现了分发到后端服务器，所以假如你没有特殊额外的需求，完全可以使用TeaWeb代替nginx。

## TeaWeb怎样配置与php-fpm配合支持PHP呢？
可以在路径规则中使用Fastcgi配置，[请在这里查看相关文档](../proxy/Fastcgi.md)。

## 系统提示server selection timeout
出现这种提示的时候，说明MongoDB连接失败，请检查MongoDb连接，可以在界面右上角"设置" > MongoDB中查看MongoDB错误信息。

## 登录系统时，用户名密码输入成功，但一直停留在登录页
我们使用文件记录用户的登录信息，请检查TeaWeb安装目录下的`web/tmp/`目录的权限是否设置正确，启动TeaWeb的用户是否有权限写入，如果没有权限写入，请设置相关权限。在Linux上最简单的是设置为777：
~~~
chmod -R 777 web/tmp/
~~~

如果`tmp/`目录不存在，请创建此目录：
~~~
teaweb-v0.0.8/
  bin/
  configs/
  ...
  web/
     tmp/
  ...
~~~

## 日志中的时间错误
在Linux服务器上，可能会发现系统日志或者代理的访问日志时间发生了错误，首先我们用`date`命令确认当前服务器的时间是否正确，在服务器上运行：
~~~bash
date
~~~
如果结果类似于：
~~~
Fri Feb 21 10:31:33 CST 2020
~~~
中文的有其他格式，确认一下这个打印出来的结果是否正确，如果不正确，你可能需要使用`ntpdate`或者`rdate`同步一下系统时间。

如果打印出来的结果是正确的，则说明启动TeaWeb时，可能环境变量中的时区设置不正确，请先设置时区后再启动：
~~~bash
export TZ=Asia/Shanghai
bin/teaweb start
~~~

当然，你可以修改`TZ`，将时区设置成别的代号，完整的时区列表可以在互联网上找到，能访问维基百科的可以在[这里](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)查看到。
