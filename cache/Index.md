# 缓存
TeaWeb中内置了一组缓存策略可以将请求结果缓存在不同的存储媒介中，目前支持以下几种存储媒介：
* 内存
* 文件
* Redis
* LevelDB，在v0.1.1中加入

## 缓存相关变量
从v0.1.5开始，可以在自定义响应Header中使用一些缓存相关的变量：
* `${cache.status}` - 缓存状态，值可能为：
  * `BYPASS` - 没有开启缓存策略或者其他原因未通过缓存策略处理的时候，状态为`BYPASS`
  * `HIT` - 已命中缓存
  * `MISS` - 未命中缓存
  * `PURGE` - 正在清除缓存
* `${cache.policy.name}` - 缓存策略名称
* `${cache.policy.type}` - 缓存策略类型（memory、redis之类） 
