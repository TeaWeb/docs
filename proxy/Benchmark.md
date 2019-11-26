# 性能测试
可以使用[`wrk`](https://github.com/wg/wrk)或其他工具（`ab`命令比较老旧，不建议使用）对TeaWeb进行压力性能测试。

以下拿一个虚拟机作为示例:
* 硬件：配置为2G内存、双核CPU，单核频率为2.4G
* 操作系统：CentOS v7.5.1804 
* TeaWeb：版本为v0.1.8

## 命令说明
`-c`为并发连接数，`-t`为线程数，`-d`为测试持续时间，默认单位为秒。

## 静态文件测试
文件尺寸为：516B，测试命令：
~~~bash
/opt/wrk -c 1000 -t 16 -d 60 "http://192.168.2.30:8081/index.html"
~~~

开启日志和统计的测试结果：
~~~
Running 1m test @ http://192.168.2.30:8081/index.html
  16 threads and 1000 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    92.37ms   75.08ms 896.79ms   68.53%
    Req/Sec   741.97    188.51     2.48k    79.70%
  708650 requests in 1.00m, 348.72MB read
Requests/sec:  11797.25
~~~

关闭日志和统计的测试结果：
~~~
Running 1m test @ http://192.168.2.30:8081/index.html
  16 threads and 1000 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    48.80ms   11.92ms 143.85ms   85.50%
    Req/Sec     1.28k   121.86     2.19k    69.84%
  1218313 requests in 1.00m, 599.53MB read
Requests/sec:  20278.17
Transfer/sec:      9.98MB
~~~

## 代理测试
代理后端的一个用Apache服务的gif图片文件，尺寸为2.6kb，Apache服务同TeaWeb在同一台服务器上，测试命令：
~~~bash
/opt/wrk -c 1000 -t 16 -d 60 "http://192.168.2.30:8081/images/apache_pb.gif"
~~~

开启日志和统计的测试结果：
~~~
Running 1m test @ http://192.168.2.30:8081/images/apache_pb.gif
  16 threads and 1000 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   220.60ms   79.02ms 810.65ms   88.32%
    Req/Sec   285.02    109.75   550.00     70.08%
  271933 requests in 1.00m, 678.58MB read
Requests/sec:   4525.87
Transfer/sec:     11.29MB
~~~

关闭日志和统计的测试结果：
~~~
Running 1m test @ http://192.168.2.30:8081/images/apache_pb.gif
  16 threads and 1000 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   151.39ms   18.79ms 539.18ms   74.86%
    Req/Sec   411.13     87.49   787.00     67.26%
  393091 requests in 1.00m, 0.96GB read
Requests/sec:   6541.07
Transfer/sec:     16.32MB
~~~

当然，具体测试的时候，后端服务最好是静态文件，以便消除因为后端服务的速度太慢而导致测试结果低下的问题。

## 资源释放情况
测试完成后，内存迅速恢复到95M左右，CPU恢复到5%以下。
