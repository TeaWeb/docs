# Docker
可以使用Docker来部署TeaWeb，[tossp](https://github.com/tossp/teaweb-build)为TeaWeb创建了一个即时更新的Docker版本，可以在 [https://hub.docker.com/r/tossp/teaweb](https://hub.docker.com/r/tossp/teaweb) 获取。

## 新手指导
### 启动容器实例
先执行以下命令拉取镜像：
~~~bash
docker pull tossp/teaweb
~~~
如果成功的话，控制台会打印类似以下的提示：
~~~
Using default tag: latest
latest: Pulling from tossp/teaweb
7692c7e2a2d0: Pull complete 
ccf074d31832: Pull complete 
be5aaf669c9a: Pull complete 
Digest: sha256:7b8634609e3bf4242749a2c1611d2e77a242848491065c462fdb7da6a6bafb26
Status: Downloaded newer image for tossp/teaweb:latest
~~~

然后用以下命令启动镜像的一个实例（容器）：
~~~bash
docker run -d -p 7777:7777 --name teaweb  tossp/teaweb:latest
~~~
如果成功的话，会提示类似于以下的实例ID：
~~~
0bd09be0f298a62eba733c6143b5d5f4ee3b1b159ad8933f6bfc4f14e3088db2
~~~

我们可以通过`docker ps -a`命令查看启动的实例状态：
~~~bash
docker ps -a
~~~
会出现：
~~~
CONTAINER ID        IMAGE                 COMMAND                CREATED             STATUS              PORTS                    NAMES
0bd09be0f298        tossp/teaweb:latest   "/teaweb/bin/teaweb"   12 seconds ago      Up 11 seconds       0.0.0.0:7777->7777/tcp   teaweb
~~~

这样就说明我们成功了，可以打开浏览器，访问 `http://127.0.0.1:7777` 来开启TeaWeb之旅。

### 持久化
如果想将Docker中的数据持久化，不至于因删除实例而消失，可以使用以下命令：
~~~bash
# 以下代码来自tossp

# 初始化关键目录（仅初次使用需要）
mkdir -p ${PWD}/data/{backups,configs,logs}
 
# 复制初始配置文件（仅初次使用需要）
docker run -it --rm -v ${PWD}/data:/data --entrypoint cp tossp/teaweb -rf /teaweb/configs /data

# 启动服务器
docker run -it --rm -p 7777:7777 -v ${PWD}/data/backups:/teaweb/backups -v ${PWD}/data/configs:/teaweb/configs -v ${PWD}/data/logs:/teaweb/logs tossp/teaweb
~~~

这样就将`backups`、`configs`、`logs`三个目录下的数据持久化到Docker之外的磁盘空间。

### 停止Docker实例
如果想停止Docker实例，请使用以下命令：
~~~bash
docker stop 0bd09be0f298
~~~
其中`0bd09be0f298`换成你实际启动的实例ID。

可以使用`docker ps -a`来查看你已经启动的所有Docker实例ID或者查看实例状态。

### 删除Docker实例
如果想删除已创建Docker实例，请使用以下命令：
~~~bash
docker rm 0bd09be0f298
~~~
其中`0bd09be0f298`换成你实际启动的实例ID。

可以使用`docker ps -a`来查看你已经启动的所有Docker实例ID或者查看实例状态。