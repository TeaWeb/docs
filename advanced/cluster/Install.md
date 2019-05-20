# 安装集群控制台

## 安装
从 [http://teaos.cn/download#cluster](http://teaos.cn/download#cluster)下载最新版本的对应平台的Cluster控制台，下载后的文件名类似于：
~~~
teaweb-cluster-linux-amd64-v1.0.0.zip
~~~

然后解压后并启动：
~~~bash
unzip teaweb-cluster-linux-amd64-v1.x.x.zip 
cd teaweb-cluster-v1.0.0/
bin/teaweb-cluster start
~~~
将其中的压缩包的文件名、版本换成你实际下载的压缩包文件名、版本。

如果启动成功，输出的结果应该类似于：
~~~
TeaWeb Cluster started ok, pid: 44124
~~~

然后在浏览器上访问：
~~~
http://127.0.0.1:7780
~~~
即可访问集群控制台界面，默认的用户名为`admin`，密码为`123456`，如果服务不是安装在本机，可以将其中的`127.0.0.1`换成实际服务器的IP地址，然后将`7780`、`7781`两个端口加入到防火墙的允许通过名单中。

如果想查看运行日志，可以在`logs/run.log`找到：
~~~bash
tail -f logs/run.log
~~~

## 配置控制台
### 修改控制台访问地址
可以修改 `configs/server.conf` 中的控制台访问地址：
~~~yaml
...
# http
http:
  "on": true
  listen: [ "0.0.0.0:7780" ]
...  
~~~

修改后重启服务后生效：
~~~bash
bin/teaweb-cluster restart
~~~

### 修改集群通讯地址
可以修改 `configs/config.yml` 中的集群通讯地址，这个地址在配置节点的时候需要用到：
~~~yaml
bind: "0.0.0.0:7781"
~~~

修改后重启服务后生效：
~~~bash
bin/teaweb-cluster restart
~~~

节点需要通过此网络地址和集群控制台通讯，所以需要将`7781	`端口加入到防火墙通过名单中（通常是节点服务器的出站策略、集群控制台服务器的入站策略）。

### 修改控制台界面登录用户名、密码
可以修改`configs/admin.yml`中的`users`下面的`username`和`password`，分别代表控制台界面登录的用户名、密码，比如将密码改成`654321`：
~~~yaml
...
users:
  - username: admin
    password: 654321
~~~

修改后重启服务后生效：
~~~bash
bin/teaweb-cluster restart
~~~

## 常用命令行下命令选项
以下是一些常用的命令行下的命令选项
~~~bash
# 打印帮助信息
./bin/teaweb-cluster -h

# 打印版本信息
./bin/teaweb-cluster -v

# 在后台运行
./bin/teaweb-cluster start

# 停止运行 
./bin/teaweb-cluster stop

# 重启
./bin/teaweb-cluster restart

# 打印服务状态
./bin/teaweb-cluster status
~~~

## 查看运行日志
如果想查看运行日志，可以在 `logs/run.log` 找到，使用 `tail` 命令查看：
~~~bash
tail -f logs/run.log
~~~

## 将teaweb-cluster加入到启动服务
在linux系统下，为了让系统重启时自动能启动我们的`teaweb-cluster`服务，可以将teaweb-cluster放入到系统的启动服务中：
1. 用编辑器 或 `vi` 打开启动脚本文件 `scripts/teaweb-cluster`；
2. 修改启动脚本中的 `INSTALL_DIR为实际的控制台的安装目录；
3. 将启动脚本文件拷贝到 `/etc/init.d` 目录下；
4. 使用 `root` 设置权限：`chmod u+x /etc/init.d/teaweb-cluster`；
5. 使用 `chkconfig` 添加到启动项中：`chkconfig --add teaweb-cluster`。

现在你就可以使用以下命令了：
~~~bash
service teaweb-cluster start|stop|restart|status
~~~

