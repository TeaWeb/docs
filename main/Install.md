# 安装
## 安装 
### 下载安装包安装
1. 可以从 [http://teaos.cn/download](http://teaos.cn/download) 下载对应的Release版本，目前支持MacOS(darwin)、Linux、Windows三种版本；
2. 使用unzip解压到某个目录，比如 teaweb-v0.0.1/；
3. 然后执行：
    ~~~bash
    cd teaweb-v0.0.1/  # 转到teaweb目录
    bin/teaweb start
    ~~~
    如果是Windows，则可以直接运行安装目录下的`start.bat`；
4. 如果没有出现错误的话，可以在浏览器中访问：
    ~~~
    http://127.0.0.1:7777
    ~~~
    其中`127.0.0.1`可能需要换成你服务器的IP，而且我们默认使用了`7777`端口（可以在`configs/server.conf`中修改），如果访问遇到了问题，请检查防火墙设置；
5. 使用用户名`admin`和密码`123456`登录，可以在`configs/admin.conf`中修改这些信息，也可以在设置界面中修改；
6. 如果是Unix或者Linux，请确保安装目录下的`configs/`和`web/tmp/`是有读取和写入权限的。
7. [设置MongoDB](#mongodb)或别的数据库。

### 使用脚本安装
在AMD、Intel等CPU上的Linux服务器上可以使用：
~~~bash
curl -s http://teaos.cn/teaweb-install.sh|sudo bash
~~~
快速自动下载对应的安装包并安装，安装后的目录为 `/usr/local/teaweb-vx.x.x`，并自动加入到系统服务中。

## MongoDB
TeaWeb需要使用MongoDB来记录日志和其他数据，如果已经安装，可以在"设置">"MongoDB"中修改MongoDB的连接参数，具体请参考[MongoDB设置](../settings/MongoDB.md)一节。

## CentOS 7
在CentOS 7上，如果你需要使用`7777`端口，可能要在firewall中注册一个规则：
~~~bash
firewall-cmd --zone=public --add-port=7777/tcp --permanent
firewall-cmd --reload
~~~

## Red Hat Enterprise Linux Server 7
在Red Hat Enterprise Linux Server 7上，如果你需要使用`7777`端口，可能要在firewall中注册一个规则：
~~~bash
firewall-cmd --zone=public --add-port=7777/tcp --permanent
firewall-cmd --reload
~~~

## Windows
Windows版本的目录下自带有 *start.bat* ，请解压后，直接双击运行 *start.bat* 即可。

## 开机启动脚本
通常我们在安装软件后，希望能随开机启动，以免重启时忘了启动服务。

### 自动安装
从v0.1.6开始，在Windows下可以运行`bin\`目录下的`service-install.exe`和`service-uninstall.exe`两个命令，分别是安装服务和卸载服务；如果后期TeaWeb安装目录改变了，需要先卸载服务再重新安装，以便服务能找到正确的TeaWeb目录。如果提示权限错误，以管理员身份运行这两个命令（通常在鼠标右键有"以管理员身份运行"）。如果提示`A system shutdown is in process`，则试着转到`bin\`目录下重新运行命令尝试。

在Linux下可以运行`bin/`下的`service-install`和`service-uninstall`两个命令，分别是安装服务和卸载服务；如果后期TeaWeb安装目录改变了，可以重新运行服务安装命令，以便服务能找到正确的TeaWeb目录。

### 手动安装
在v0.1.6之前，Linux二进制发行版自带启动脚本模板，可以在 *scripts/* 目录下找到：
~~~
teaweb - teaweb启动脚本 
teaweb-agent - agent启动脚本
~~~

使用步骤为：
1. 修改启动脚本中的`INSTALL_DIR`为实际的TeaWeb或Agent安装目录
2. 将启动脚本文件拷贝到 */etc/init.d* 目录下
3. 使用`root`设置权限：`chmod u+x /etc/init.d/teaweb` 或者 `chmod u+x /etc/init.d/teaweb-agent`
4. 使用`chkconfig`添加到启动项中：`chkconfig --add teaweb` 或者 `chkconfig --add teaweb-agent`

现在你就可以使用以下命令了：
~~~bash
service teaweb start|stop|restart|reset
service teaweb-agent start|stop|restart
~~~

而且开机启动的时候会自动执行：
~~~bash
service teaweb start
service teaweb-agent start
~~~