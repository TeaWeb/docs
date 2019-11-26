# 代理服务上下文
可以在Javascript中使用`context`来访问代理服务的上下文信息。

示例1：打印Server信息：
~~~javascript
console.log(context.server);
~~~

示例2：根据Backend ID来查找一个后端服务器信息（从v0.1.9开始）：
~~~javascript
var backend = context.server.findBackend("0biKxy56Y4sUoo9Z");
console.log(backend.address);
~~~

## http.Server对象
~~~javascript
http.Server = function (options) {
	this.isOn = true;
	this.id = "";
	this.filename = "";
	this.name = [];
	this.description = "";
	this.listen = [];
	this.backends = [];
	this.locations = [];
	this.http = true;
	this.ssl = {};
    
    // 查找后端服务器
	this.findBackend = function (backendId) {};
    
    // 查找路径规则
    this.findLocation = function (locationId) {};

};
~~~

## http.Backend对象
~~~javascript
http.Backend = function (options) {
	this.isOn = true;
	this.id = "";
	this.address = "";
	this.weight = 0;
	this.isDown = false;
	this.isBackup = false;
	this.name = [];
	this.code = "";
};
~~~

## http.Location对象
~~~javascript
http.Location = function (options) {
    this.isOn = true;
    this.pattern = "";
    this.cachePolicy = "";
    this.fastcgi = [];
    this.id = "";
    this.index = [];
    this.root = "";
    this.rewrite = [];
    this.websocket = {};
    this.backends = [];

    this.findBackend = function (backendId) {};
}
~~~

## http.Fastcgi对象
~~~javascript
http.Fastcgi = function (options) {
	this.id = "";
	this.isOn = true;
	this.pass = "";
};
~~~

## http.Rewrite对象
~~~javascript
http.Rewrite = function (options) {
	this.id = "";
	this.isOn = true;
	this.pattern = "";
	this.replace = "";
};
~~~
