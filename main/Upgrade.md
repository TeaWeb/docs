# 升级

## 手动升级
1. 下载新版本对应你的系统的二进制版本zip文件，并解压；
2. 停止正在运行的TeaWeb服务，可以在原有目录下运行 `bin/teaweb stop`；
3. 将 **除configs/** 目录外的所有文件拷贝到原有目录下，并替换原有文件；
4. 使用命令 `bin/teaweb restart` 重启服务，升级完成。

## 使用脚本升级
在Linux环境下，可以使用自带的`upgrade.sh`进行升级，分成两个步骤：
1. 在[官网](http://teaos.cn/download)上下载最新版本的TeaWeb，传至服务器的某个目录，比如叫`/root/`目录下，然后使用`unzip`解压，比如解压后的目录是`/root/teaweb-v0.1.6`
2. 在 *老版本* 的安装目录下运行：
~~~bash
./upgrade.sh /root/teaweb-v0.1.6
~~~
即可。其中`/root/teaweb-v0.1.6`换成你自己解压的新版本的TeaWeb目录。

## v0.1.3
从 v0.1.3开始，将先前根目录下的很多目录合并到`web/`目录下，以下是新旧对比：

v0.1.2及以前：
~~~
根目录/
   bin/
   configs/
   logs/
   plugins/
   scripts/
   installers/
   libs/
   public/
   resources/
   tmp/
   upgrade/
   views/
~~~

v0.1.3以后：
~~~
根目录/
   bin/
   configs/
   logs/
   plugins/
   scripts/
   web/
      installers/
      libs/
      public/
      resources/
      tmp/
      upgrade/
      views/
~~~