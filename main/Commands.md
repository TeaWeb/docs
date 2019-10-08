# 常用命令
## TeaWeb控制
### 打印帮助信息
~~~bash
./bin/teaweb -h
~~~

### 打印版本信息
~~~bash
./bin/teaweb -v
~~~

### 启动服务
启动服务并在后台运行：
~~~bash
./bin/teaweb start
~~~

如果要在前端启动服务，并阻塞当前进程，可以使用：
~~~bash
./bin/teaweb
~~~

### 停止服务
~~~bash
./bin/teaweb stop
~~~

### 重启服务
~~~bash
./bin/teaweb restart
~~~

### 重新加载代理配置
v0.1以后支持
~~~bash
./bin/teaweb reload
~~~

### 重置服务状态
v0.0.8以后支持
~~~bash
./bin/teaweb reset
~~~

### 查看服务状态
v0.1以后支持
~~~bash
./bin/teaweb status
~~~

### 开启pprof
从v0.1.7开始，可以使用以下命令开启pprof模式，用来监控TeaWeb运行性能信息：
~~~bash
./bin/teaweb pprof
~~~
默认pprof地址为`:6060`

启动后可以在浏览器上访问这个地址，比如 `http://127.0.0.1:6060/debug/pprof/` ，或者使用`go tool pprof`命令来查看，比如查看所有alloc的heap信息：
~~~bash
go tool pprof -alloc_space  "http://127.0.0.1:6060/debug/pprof/heap"
~~~

查看正在使用的内存空间：
~~~bash
go tool pprof -inuse_space  "http://127.0.0.1:6060/debug/pprof/heap"
~~~

查看CPU调用信息：
~~~bash
go tool pprof  "http://127.0.0.1:6060/debug/pprof/profile"
~~~

还有更多的示例可以参考 [https://jvns.ca/blog/2017/09/24/profiling-go-with-pprof/](https://jvns.ca/blog/2017/09/24/profiling-go-with-pprof/)。

你可以指定别的地址：
~~~bash
./bin/teaweb pprof 127.0.0.1:8888
~~~

### 集群同步
从v0.1.8开始，可以使用以下命令跟集群同步：
~~~bash
./bin/teaweb sync
~~~
如果是Master节点，则会自动将本地的配置同步到集群，同步时，只要在`configs/`下的配置文件都会被同步，所以你可以在`configs/`下加入自己的配置文件，以便利用集群同步到其他节点。

如果是Slave节点，则自动从集群同步配置到本地。


## 系统服务
可以以系统服务的方式管理TeaWeb。

### 安装系统服务
从v0.1.6开始，Linux和Windows支持：
~~~bash
./bin/service-install
~~~

在Linux上，此命令需要使用`root`分组的用户操作，所以你可能需要切换到`root`账号，或者使用`sudo ...`来运行。

### 卸载系统服务
从v0.1.6开始，Linux和Windows支持：
~~~bash
./bin/service-uninstall
~~~

在Linux上，此命令需要使用`root`分组的用户操作，所以你可能需要切换到`root`账号，或者使用`sudo ...`来运行。