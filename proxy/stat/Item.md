# 数据指标
TeaWeb内置了一组数据指标，可以在自定义统计图表时使用。

相关的几个概念：
* `代号` - 指标代号用来区分指标，很多时候根据不同的时间单位会有多个代号
* `参数` - 指标的参数用来标识指标的统计项目，比如"浏览器统计"就会使用浏览器名称和浏览器主版本来作为单类浏览器的标识
* `统计数据` - 指标对每个统计项目的数量统计结果  

## 内置数据指标
### 请求数统计（秒） - request.all.second
所有请求的请求数统计。

参数：无。

统计数据：
* `count` - 请求数

### 请求数统计（分钟） - request.all.minute
所有请求的请求数统计。

参数：无。

统计数据：
* `count` - 请求数

### 请求数统计（小时） - request.all.hour
所有请求的请求数统计。

参数：无。

统计数据：
* `count` - 请求数

### 请求数统计（天） - request.all.day
所有请求的请求数统计。

参数：无。

统计数据：
* `count` - 请求数

### 请求数统计（周） - request.all.week
所有请求的请求数统计。

参数：无。

统计数据：
* `count` - 请求数

### 请求数统计（月） - request.all.month
所有请求的请求数统计。

参数：无。

统计数据：
* `count` - 请求数

### 请求数统计（年） - request.all.year
所有请求的请求数统计。

参数：无。

统计数据：
* `count` - 请求数

### URL请求数统计（秒） - request.page.second
单个URL请求数统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL请求数统计（分钟） - request.page.minute
单个URL请求数统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL请求数统计（小时） - request.page.hour
单个URL请求数统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL请求数统计（天） - request.page.day
单个URL请求数统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL请求数统计（周） - request.page.week
单个URL请求数统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL请求数统计（月） - request.page.month
单个URL请求数统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL请求数统计（年） - request.page.year
单个URL请求数统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### IP请求数排行（小时） - request.ip.hour
所有请求的IP请求数排行。

参数：无。

统计数据：
* `top` - IP及请求数列表

### IP请求数排行（天） - request.ip.day
所有请求的IP请求数排行。

参数：无。

统计数据：
* `top` - IP及请求数列表

### 状态码统计（秒） - status.all.second
所有请求的响应状态码统计。

参数：
* `status` - HTTP状态码

统计数据：
* `count` - 请求数量

### 状态码统计（分钟） - status.all.minute
所有请求的响应状态码统计。

参数：
* `status` - HTTP状态码

统计数据：
* `count` - 请求数量

### 状态码统计（小时） - status.all.hour
所有请求的响应状态码统计。

参数：
* `status` - HTTP状态码

统计数据：
* `count` - 请求数量

### 状态码统计（天） - status.all.day
所有请求的响应状态码统计。

参数：
* `status` - HTTP状态码

统计数据：
* `count` - 请求数量

### 状态码统计（周） - status.all.week
所有请求的响应状态码统计。

参数：
* `status` - HTTP状态码

统计数据：
* `count` - 请求数量

### 状态码统计（月） - status.all.month
所有请求的响应状态码统计。

参数：
* `status` - HTTP状态码

统计数据：
* `count` - 请求数量

### 状态码统计（年） - status.all.year
所有请求的响应状态码统计。

参数：
* `status` - HTTP状态码

统计数据：
* `count` - 请求数量

### URL状态码统计（秒） - status.page.second
单个URL响应状态码统计。

参数：
* `status` - HTTP状态码
* `page` - 请求URL

统计数据：
* `count` - 请求数量

### URL状态码统计（分钟） - status.page.minute
单个URL响应状态码统计。

参数：
* `status` - HTTP状态码
* `page` - 请求URL

统计数据：
* `count` - 请求数量

### URL状态码统计（小时） - status.page.hour
单个URL响应状态码统计。

参数：
* `status` - HTTP状态码
* `page` - 请求URL

统计数据：
* `count` - 请求数量

### URL状态码统计（天） - status.page.day
单个URL响应状态码统计。

参数：
* `status` - HTTP状态码
* `page` - 请求URL

统计数据：
* `count` - 请求数量

### URL状态码统计（周） - status.page.week
单个URL响应状态码统计。

参数：
* `status` - HTTP状态码
* `page` - 请求URL

统计数据：
* `count` - 请求数量

### URL状态码统计（月） - status.page.month
单个URL响应状态码统计。

参数：
* `status` - HTTP状态码
* `page` - 请求URL

统计数据：
* `count` - 请求数量

### URL状态码统计（年） - status.page.year
单个URL响应状态码统计。

参数：
* `status` - HTTP状态码
* `page` - 请求URL

统计数据：
* `count` - 请求数量

### 流量统计（秒） - traffic.all.second
所有请求的流量统计。

参数：无。

统计数据：
* `bytes` - 流量（字节）

### 流量统计（分钟） - traffic.all.minute
所有请求的流量统计。

参数：无。

统计数据：
* `bytes` - 流量（字节）

### 流量统计（小时） - traffic.all.hour
所有请求的流量统计。

参数：无。

统计数据：
* `bytes` - 流量（字节）

### 流量统计（天） - traffic.all.day
所有请求的流量统计。

参数：无。

统计数据：
* `bytes` - 流量（字节）

### 流量统计（周） - traffic.all.week
所有请求的流量统计。

参数：无。

统计数据：
* `bytes` - 流量（字节）

### 流量统计（月） - traffic.all.month
所有请求的流量统计。

参数：无。

统计数据：
* `bytes` - 流量（字节）

### 流量统计（年） - traffic.all.year
所有请求的流量统计。

参数：无。

统计数据：
* `bytes` - 流量（字节）

### URL流量统计（秒） - traffic.page.second
单个URL流量统计。

参数：
* `page` - 请求URL

统计数据：
* `bytes` - 流量（字节）

### URL流量统计（分钟） - traffic.page.minute
单个URL流量统计。

参数：
* `page` - 请求URL

统计数据：
* `bytes` - 流量（字节）

### URL流量统计（小时） - traffic.page.hour
单个URL流量统计。

参数：
* `page` - 请求URL

统计数据：
* `bytes` - 流量（字节）

### URL流量统计（天） - traffic.page.day
单个URL流量统计。

参数：
* `page` - 请求URL

统计数据：
* `bytes` - 流量（字节）

### URL流量统计（周） - traffic.page.week
单个URL流量统计。

参数：
* `page` - 请求URL

统计数据：
* `bytes` - 流量（字节）

### URL流量统计（月） - traffic.page.month
单个URL流量统计。

参数：
* `page` - 请求URL

统计数据：
* `bytes` - 流量（字节）

### URL流量统计（年） - traffic.page.year
单个URL流量统计。

参数：
* `page` - 请求URL

统计数据：
* `bytes` - 流量（字节）

### PV统计（秒） - pv.all.second
所有请求的PV统计。

参数：无。

统计数据：
* `count` - PV数

### PV统计（分钟） - pv.all.minute
所有请求的PV统计。

参数：无。

统计数据：
* `count` - PV数

### PV统计（小时） - pv.all.hour
所有请求的PV统计。

参数：无。

统计数据：
* `count` - PV数

### PV统计（天） - pv.all.day
所有请求的PV统计。

参数：无。

统计数据：
* `count` - PV数

### PV统计（周） - pv.all.week
所有请求的PV统计。

参数：无。

统计数据：
* `count` - PV数

### PV统计（月） - pv.all.month
所有请求的PV统计。

参数：无。

统计数据：
* `count` - PV数

### PV统计（年） - pv.all.year
所有请求的PV统计。

参数：无。

统计数据：
* `count` - PV数

### URL PV统计（秒） - pv.page.second
单个URL PV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - PV数

### URL PV统计（分钟） - pv.page.minute
单个URL PV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - PV数

### URL PV统计（小时） - pv.page.hour
单个URL PV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - PV数

### URL PV统计（天） - pv.page.day
单个URL PV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - PV数

### URL PV统计（周） - pv.page.week
单个URL PV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - PV数

### URL PV统计（月） - pv.page.month
单个URL PV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - PV数

### URL PV统计（年） - pv.page.year
单个URL PV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - PV数

### UV统计（秒） - uv.all.second
所有请求的UV统计。

参数：无。

统计数据：
* `count` - UV数

### UV统计（分钟） - uv.all.minute
所有请求的UV统计。

参数：无。

统计数据：
* `count` - UV数

### UV统计（小时） - uv.all.hour
所有请求的UV统计。

参数：无。

统计数据：
* `count` - UV数

### UV统计（天） - uv.all.day
所有请求的UV统计。

参数：无。

统计数据：
* `count` - UV数

### UV统计（周） - uv.all.week
所有请求的UV统计。

参数：无。

统计数据：
* `count` - UV数

### UV统计（月） - uv.all.month
所有请求的UV统计。

参数：无。

统计数据：
* `count` - UV数

### UV统计（年） - uv.all.year
所有请求的UV统计。

参数：无。

统计数据：
* `count` - UV数

### URL UV统计（秒） - uv.page.second
单个URL UV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - UV数量

### URL UV统计（分钟） - uv.page.minute
单个URL UV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - UV数量

### URL UV统计（小时） - uv.page.hour
单个URL UV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - UV数量

### URL UV统计（天） - uv.page.day
单个URL UV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - UV数量

### URL UV统计（周） - uv.page.week
单个URL UV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - UV数量

### URL UV统计（月） - uv.page.month
单个URL UV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - UV数量

### URL UV统计（年） - uv.page.year
单个URL UV统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - UV数量

### IP数统计（秒） - ip.all.second
所有请求的IP数统计。

参数：无。

统计数据：
* `count` - 请求数

### IP数统计（分钟） - ip.all.minute
所有请求的IP数统计。

参数：无。

统计数据：
* `count` - 请求数

### IP数统计（小时） - ip.all.hour
所有请求的IP数统计。

参数：无。

统计数据：
* `count` - 请求数

### IP数统计（天） - ip.all.day
所有请求的IP数统计。

参数：无。

统计数据：
* `count` - 请求数

### IP数统计（周） - ip.all.week
所有请求的IP数统计。

参数：无。

统计数据：
* `count` - 请求数

### IP数统计（月） - ip.all.month
所有请求的IP数统计。

参数：无。

统计数据：
* `count` - 请求数

### IP数统计（年） - ip.all.year
所有请求的IP数统计。

参数：无。

统计数据：
* `count` - 请求数

### URL IP统计（秒） - ip.page.second
单个URL IP统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL IP统计（分钟） - ip.page.minute
单个URL IP统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL IP统计（小时） - ip.page.hour
单个URL IP统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL IP统计（天） - ip.page.day
单个URL IP统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL IP统计（周） - ip.page.week
单个URL IP统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL IP统计（月） - ip.page.month
单个URL IP统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL IP统计（年） - ip.page.year
单个URL IP统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### 请求方法统计（秒） - method.all.second
所有请求的请求方法统计。

参数：
* `method` - 请求方法（大写）

统计数据：
* `count` - 请求数

### 请求方法统计（分钟） - method.all.minute
所有请求的请求方法统计。

参数：
* `method` - 请求方法（大写）

统计数据：
* `count` - 请求数

### 请求方法统计（小时） - method.all.hour
所有请求的请求方法统计。

参数：
* `method` - 请求方法（大写）

统计数据：
* `count` - 请求数

### 请求方法统计（天） - method.all.day
所有请求的请求方法统计。

参数：
* `method` - 请求方法（大写）

统计数据：
* `count` - 请求数

### 请求方法统计（周） - method.all.week
所有请求的请求方法统计。

参数：
* `method` - 请求方法（大写）

统计数据：
* `count` - 请求数

### 请求方法统计（月） - method.all.month
所有请求的请求方法统计。

参数：
* `method` - 请求方法（大写）

统计数据：
* `count` - 请求数

### 请求方法统计（年） - method.all.year
所有请求的请求方法统计。

参数：
* `method` - 请求方法（大写）

统计数据：
* `count` - 请求数

### URL请求方法统计（秒） - method.page.second
单个URL请求方法统计。

参数：
* `method` - 请求方法
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL请求方法统计（分钟） - method.page.minute
单个URL请求方法统计。

参数：
* `method` - 请求方法
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL请求方法统计（小时） - method.page.hour
单个URL请求方法统计。

参数：
* `method` - 请求方法
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL请求方法统计（天） - method.page.day
单个URL请求方法统计。

参数：
* `method` - 请求方法
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL请求方法统计（周） - method.page.week
单个URL请求方法统计。

参数：
* `method` - 请求方法
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL请求方法统计（月） - method.page.month
单个URL请求方法统计。

参数：
* `method` - 请求方法
* `page` - 请求URL

统计数据：
* `count` - 请求数

### URL请求方法统计（年） - method.page.year
单个URL请求方法统计。

参数：
* `method` - 请求方法
* `page` - 请求URL

统计数据：
* `count` - 请求数

### 耗时统计（秒） - cost.all.second
所有请求的耗时统计。

参数：无。

统计数据：
* `countReq` - 请求数
* `cost` - 耗时（秒）

### 耗时统计（分钟） - cost.all.minute
所有请求的耗时统计。

参数：无。

统计数据：
* `countReq` - 请求数
* `cost` - 耗时（秒）

### 耗时统计（小时） - cost.all.hour
所有请求的耗时统计。

参数：无。

统计数据：
* `countReq` - 请求数
* `cost` - 耗时（秒）

### 耗时统计（天） - cost.all.day
所有请求的耗时统计。

参数：无。

统计数据：
* `countReq` - 请求数
* `cost` - 耗时（秒）

### 耗时统计（周） - cost.all.week
所有请求的耗时统计。

参数：无。

统计数据：
* `countReq` - 请求数
* `cost` - 耗时（秒）

### 耗时统计（月） - cost.all.month
所有请求的耗时统计。

参数：无。

统计数据：
* `countReq` - 请求数
* `cost` - 耗时（秒）

### 耗时统计（年） - cost.all.year
所有请求的耗时统计。

参数：无。

统计数据：
* `countReq` - 请求数
* `cost` - 耗时（秒）

### URL耗时统计（秒） - cost.page.second
单个URL耗时统计。

参数：
* `page` - 请求URL

统计数据：
* `countReq` - 请求数
* `cost` - 耗时

### URL耗时统计（分钟） - cost.page.minute
单个URL耗时统计。

参数：
* `page` - 请求URL

统计数据：
* `countReq` - 请求数
* `cost` - 耗时

### URL耗时统计（小时） - cost.page.hour
单个URL耗时统计。

参数：
* `page` - 请求URL

统计数据：
* `countReq` - 请求数
* `cost` - 耗时

### URL耗时统计（天） - cost.page.day
单个URL耗时统计。

参数：
* `page` - 请求URL

统计数据：
* `countReq` - 请求数
* `cost` - 耗时

### URL耗时统计（周） - cost.page.week
单个URL耗时统计。

参数：
* `page` - 请求URL

统计数据：
* `countReq` - 请求数
* `cost` - 耗时

### URL耗时统计（月） - cost.page.month
单个URL耗时统计。

参数：
* `page` - 请求URL

统计数据：
* `countReq` - 请求数
* `cost` - 耗时

### URL耗时统计（年） - cost.page.year
单个URL耗时统计。

参数：
* `page` - 请求URL

统计数据：
* `countReq` - 请求数
* `cost` - 耗时

### 来源域名统计（秒） - referer.domain.second
所有请求的来源域名统计。

参数：
* `domain` - 域名

统计数据：
* `count` - 请求数

### 来源域名统计（分钟） - referer.domain.minute
所有请求的来源域名统计。

参数：
* `domain` - 域名

统计数据：
* `count` - 请求数

### 来源域名统计（小时） - referer.domain.hour
所有请求的来源域名统计。

参数：
* `domain` - 域名

统计数据：
* `count` - 请求数

### 来源域名统计（天） - referer.domain.day
所有请求的来源域名统计。

参数：
* `domain` - 域名

统计数据：
* `count` - 请求数

### 来源域名统计（周） - referer.domain.week
所有请求的来源域名统计。

参数：
* `domain` - 域名

统计数据：
* `count` - 请求数

### 来源域名统计（月） - referer.domain.month
所有请求的来源域名统计。

参数：
* `domain` - 域名

统计数据：
* `count` - 请求数

### 来源域名统计（年） - referer.domain.year
所有请求的来源域名统计。

参数：
* `domain` - 域名

统计数据：
* `count` - 请求数

### 来源URL统计（秒） - referer.url.second
所有请求的来源URL统计。

参数：
* `url` - 来源URL

统计数据：
* `count` - 请求数

### 来源URL统计（分钟） - referer.url.minute
所有请求的来源URL统计。

参数：
* `url` - 来源URL

统计数据：
* `count` - 请求数

### 来源URL统计（小时） - referer.url.hour
所有请求的来源URL统计。

参数：
* `url` - 来源URL

统计数据：
* `count` - 请求数

### 来源URL统计（天） - referer.url.day
所有请求的来源URL统计。

参数：
* `url` - 来源URL

统计数据：
* `count` - 请求数

### 来源URL统计（周） - referer.url.week
所有请求的来源URL统计。

参数：
* `url` - 来源URL

统计数据：
* `count` - 请求数

### 来源URL统计（月） - referer.url.month
所有请求的来源URL统计。

参数：
* `url` - 来源URL

统计数据：
* `count` - 请求数

### 来源URL统计（年） - referer.url.year
所有请求的来源URL统计。

参数：
* `url` - 来源URL

统计数据：
* `count` - 请求数

### 登陆页统计（秒） - landing.page.second
登陆页统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### 登陆页统计（分钟） - landing.page.minute
登陆页统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### 登陆页统计（小时） - landing.page.hour
登陆页统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### 登陆页统计（天） - landing.page.day
登陆页统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### 登陆页统计（周） - landing.page.week
登陆页统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### 登陆页统计（月） - landing.page.month
登陆页统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### 登陆页统计（年） - landing.page.year
登陆页统计。

参数：
* `page` - 请求URL

统计数据：
* `count` - 请求数

### 后端请求统计（秒） - backend.all.second
计算某个后端服务器请求次数。

参数：
* `backend` - 后端服务器ID

统计数据：
* `count` - 请求数

### 后端请求统计（分钟） - backend.all.minute
计算某个后端服务器请求次数。

参数：
* `backend` - 后端服务器ID

统计数据：
* `count` - 请求数

### 后端请求统计（小时） - backend.all.hour
计算某个后端服务器请求次数。

参数：
* `backend` - 后端服务器ID

统计数据：
* `count` - 请求数

### 后端请求统计（天） - backend.all.day
计算某个后端服务器请求次数。

参数：
* `backend` - 后端服务器ID

统计数据：
* `count` - 请求数

### 后端请求统计（周） - backend.all.week
计算某个后端服务器请求次数。

参数：
* `backend` - 后端服务器ID

统计数据：
* `count` - 请求数

### 后端请求统计（月） - backend.all.month
计算某个后端服务器请求次数。

参数：
* `backend` - 后端服务器ID

统计数据：
* `count` - 请求数

### 后端请求统计（年） - backend.all.year
计算某个后端服务器请求次数。

参数：
* `backend` - 后端服务器ID

统计数据：
* `count` - 请求数

### 路径规则请求统计（秒） - location.all.second
路径规则请求统计。

参数：
* `location` - 路径规则ID

统计数据：
* `count` - 请求数

### 路径规则请求统计（分钟） - location.all.minute
路径规则请求统计。

参数：
* `location` - 路径规则ID

统计数据：
* `count` - 请求数

### 路径规则请求统计（小时） - location.all.hour
路径规则请求统计。

参数：
* `location` - 路径规则ID

统计数据：
* `count` - 请求数

### 路径规则请求统计（天） - location.all.day
路径规则请求统计。

参数：
* `location` - 路径规则ID

统计数据：
* `count` - 请求数

### 路径规则请求统计（周） - location.all.week
路径规则请求统计。

参数：
* `location` - 路径规则ID

统计数据：
* `count` - 请求数

### 路径规则请求统计（月） - location.all.month
路径规则请求统计。

参数：
* `location` - 路径规则ID

统计数据：
* `count` - 请求数

### 路径规则请求统计（年） - location.all.year
路径规则请求统计。

参数：
* `location` - 路径规则ID

统计数据：
* `count` - 请求数

### 重写规则请求统计（秒） - rewrite.all.second
重写规则请求统计。

参数：
* `rewrite` - 重写规则ID

统计数据：
* `count` - 请求数

### 重写规则请求统计（分钟） - rewrite.all.minute
重写规则请求统计。

参数：
* `rewrite` - 重写规则ID

统计数据：
* `count` - 请求数

### 重写规则请求统计（小时） - rewrite.all.hour
重写规则请求统计。

参数：
* `rewrite` - 重写规则ID

统计数据：
* `count` - 请求数

### 重写规则请求统计（天） - rewrite.all.day
重写规则请求统计。

参数：
* `rewrite` - 重写规则ID

统计数据：
* `count` - 请求数

### 重写规则请求统计（周） - rewrite.all.week
重写规则请求统计。

参数：
* `rewrite` - 重写规则ID

统计数据：
* `count` - 请求数

### 重写规则请求统计（月） - rewrite.all.month
重写规则请求统计。

参数：
* `rewrite` - 重写规则ID

统计数据：
* `count` - 请求数

### 重写规则请求统计（年） - rewrite.all.year
重写规则请求统计。

参数：
* `rewrite` - 重写规则ID

统计数据：
* `count` - 请求数

### Fastcgi请求统计（秒） - fastcgi.all.second
Fastcgi请求统计。

参数：
* `fastcgi` - Fastcgi ID

统计数据：
* `count` - 请求数

### Fastcgi请求统计（分钟） - fastcgi.all.minute
Fastcgi请求统计。

参数：
* `fastcgi` - Fastcgi ID

统计数据：
* `count` - 请求数

### Fastcgi请求统计（小时） - fastcgi.all.hour
Fastcgi请求统计。

参数：
* `fastcgi` - Fastcgi ID

统计数据：
* `count` - 请求数

### Fastcgi请求统计（天） - fastcgi.all.day
Fastcgi请求统计。

参数：
* `fastcgi` - Fastcgi ID

统计数据：
* `count` - 请求数

### Fastcgi请求统计（周） - fastcgi.all.week
Fastcgi请求统计。

参数：
* `fastcgi` - Fastcgi ID

统计数据：
* `count` - 请求数

### Fastcgi请求统计（月） - fastcgi.all.month
Fastcgi请求统计。

参数：
* `fastcgi` - Fastcgi ID

统计数据：
* `count` - 请求数

### Fastcgi请求统计（年） - fastcgi.all.year
Fastcgi请求统计。

参数：
* `fastcgi` - Fastcgi ID

统计数据：
* `count` - 请求数

### 设备统计（秒） - device.all.second
所有请求的设备统计。

参数：
* `family` - 设备名
* `model` - 型号

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 设备统计（分钟） - device.all.minute
所有请求的设备统计。

参数：
* `family` - 设备名
* `model` - 型号

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 设备统计（小时） - device.all.hour
所有请求的设备统计。

参数：
* `family` - 设备名
* `model` - 型号

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 设备统计（天） - device.all.day
所有请求的设备统计。

参数：
* `family` - 设备名
* `model` - 型号

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 设备统计（周） - device.all.week
所有请求的设备统计。

参数：
* `family` - 设备名
* `model` - 型号

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 设备统计（月） - device.all.month
所有请求的设备统计。

参数：
* `family` - 设备名
* `model` - 型号

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 设备统计（年） - device.all.year
所有请求的设备统计。

参数：
* `family` - 设备名
* `model` - 型号

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 操作系统统计（秒） - os.all.second
所有请求的操作系统统计。

参数：
* `family` - 操作系统名称
* `major` - 操作系统主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 操作系统统计（分钟） - os.all.minute
所有请求的操作系统统计。

参数：
* `family` - 操作系统名称
* `major` - 操作系统主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 操作系统统计（小时） - os.all.hour
所有请求的操作系统统计。

参数：
* `family` - 操作系统名称
* `major` - 操作系统主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 操作系统统计（天） - os.all.day
所有请求的操作系统统计。

参数：
* `family` - 操作系统名称
* `major` - 操作系统主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 操作系统统计（周） - os.all.week
所有请求的操作系统统计。

参数：
* `family` - 操作系统名称
* `major` - 操作系统主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 操作系统统计（月） - os.all.month
所有请求的操作系统统计。

参数：
* `family` - 操作系统名称
* `major` - 操作系统主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 操作系统统计（年） - os.all.year
所有请求的操作系统统计。

参数：
* `family` - 操作系统名称
* `major` - 操作系统主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 浏览器统计（秒） - browser.all.second
所有请求的浏览器统计。

参数：
* `family` - 浏览器名称
* `major` - 浏览器主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 浏览器统计（分钟） - browser.all.minute
所有请求的浏览器统计。

参数：
* `family` - 浏览器名称
* `major` - 浏览器主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 浏览器统计（小时） - browser.all.hour
所有请求的浏览器统计。

参数：
* `family` - 浏览器名称
* `major` - 浏览器主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 浏览器统计（天） - browser.all.day
所有请求的浏览器统计。

参数：
* `family` - 浏览器名称
* `major` - 浏览器主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 浏览器统计（周） - browser.all.week
所有请求的浏览器统计。

参数：
* `family` - 浏览器名称
* `major` - 浏览器主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 浏览器统计（月） - browser.all.month
所有请求的浏览器统计。

参数：
* `family` - 浏览器名称
* `major` - 浏览器主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 浏览器统计（年） - browser.all.year
所有请求的浏览器统计。

参数：
* `family` - 浏览器名称
* `major` - 浏览器主版本

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 区域统计（秒） - region.all.second
所有请求的区域统计。

参数：
* `region` - 国家或地区

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 区域统计（分钟） - region.all.minute
所有请求的区域统计。

参数：
* `region` - 国家或地区

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 区域统计（小时） - region.all.hour
所有请求的区域统计。

参数：
* `region` - 国家或地区

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 区域统计（天） - region.all.day
所有请求的区域统计。

参数：
* `region` - 国家或地区

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 区域统计（周） - region.all.week
所有请求的区域统计。

参数：
* `region` - 国家或地区

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 区域统计（月） - region.all.month
所有请求的区域统计。

参数：
* `region` - 国家或地区

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 区域统计（年） - region.all.year
所有请求的区域统计。

参数：
* `region` - 国家或地区

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 省份统计（秒） - province.all.second
所有请求的省份统计。

参数：
* `region` - 国家或地区
* `province` - 省份或州

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 省份统计（分钟） - province.all.minute
所有请求的省份统计。

参数：
* `region` - 国家或地区
* `province` - 省份或州

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 省份统计（小时） - province.all.hour
所有请求的省份统计。

参数：
* `region` - 国家或地区
* `province` - 省份或州

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 省份统计（天） - province.all.day
所有请求的省份统计。

参数：
* `region` - 国家或地区
* `province` - 省份或州

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 省份统计（周） - province.all.week
所有请求的省份统计。

参数：
* `region` - 国家或地区
* `province` - 省份或州

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 省份统计（月） - province.all.month
所有请求的省份统计。

参数：
* `region` - 国家或地区
* `province` - 省份或州

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 省份统计（年） - province.all.year
所有请求的省份统计。

参数：
* `region` - 国家或地区
* `province` - 省份或州

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 城市统计（秒） - city.all.second
所有请求的城市统计。

参数：
* `region` - 国家或地区
* `province` - 省份、州
* `city` - 城市

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 城市统计（分钟） - city.all.minute
所有请求的城市统计。

参数：
* `region` - 国家或地区
* `province` - 省份、州
* `city` - 城市

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 城市统计（小时） - city.all.hour
所有请求的城市统计。

参数：
* `region` - 国家或地区
* `province` - 省份、州
* `city` - 城市

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 城市统计（天） - city.all.day
所有请求的城市统计。

参数：
* `region` - 国家或地区
* `province` - 省份、州
* `city` - 城市

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 城市统计（周） - city.all.week
所有请求的城市统计。

参数：
* `region` - 国家或地区
* `province` - 省份、州
* `city` - 城市

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 城市统计（月） - city.all.month
所有请求的城市统计。

参数：
* `region` - 国家或地区
* `province` - 省份、州
* `city` - 城市

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量

### 城市统计（年） - city.all.year
所有请求的城市统计。

参数：
* `region` - 国家或地区
* `province` - 省份、州
* `city` - 城市

统计数据：
* `countReq` - 请求数
* `countPV` - PV数量
* `countUV` - UV数量
* `countIP` - IP数量
