# API描述
读取最后N条访问日志，v0.1.8开始加入。

## API地址
~~~
/api/v1/proxy/${serverId}/accesslog/list/${size}
~~~

其中：
* `${serverId}` - 代理服务ID
* `${size}` - 读取数量，比如`10`

## 请求方法
~~~
GET
~~~

## 请求参数
无

## 返回结果示例
~~~json
{
  "accesslogs": [
    {
      "id": "5d7ded2609de0a0d51ef4da0",
      "serverId": "JnZ03pbDebcOQ7h9",
      "backendId": "0biKxy56Y4sUoo9Z",
      "locationId": "",
      "fastcgiId": "",
      "rewriteId": "",
      "teaVersion": "0.1.7.2",
      "remoteAddr": "127.0.0.1",
      "remotePort": 0,
      "remoteUser": "",
      "requestURI": "/",
      "requestPath": "/",
      "apiPath": "",
      "apiStatus": "",
      "requestLength": 0,
      "requestTime": 0.000515546,
      "requestMethod": "GET",
      "requestFilename": "",
      "scheme": "http",
      "proto": "HTTP/1.1",
      "bytesSent": 19,
      "bodyBytesSent": 19,
      "status": 200,
      "statusMessage": "",
      "sentHeader": {
        "Content-Length": [
          "19"
        ],
        "Content-Type": [
          "text/plain; charset=utf-8"
        ],
        "Date": [
          "Sun, 15 Sep 2019 07:49:56 GMT"
        ],
        "Hello": [
          "World"
        ],
        "X-Cache": [
          "BYPASS"
        ]
      },
      "timeISO8601": "2019-09-15T15:49:56.793+08:00",
      "timeLocal": "15/Sep/2019:15:49:56 +0800",
      "msec": 1.568533796793236e+09,
      "timestamp": 1568533796,
      "host": "127.0.0.1:8882",
      "referer": "",
      "userAgent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/76.0.3809.132 Safari/537.36",
      "request": "GET / HTTP/1.1",
      "contentType": "",
      "cookie": {
        "Hm_lvt_2259172a9054c42aae07421c8bbf3c84": "1566973980,1567065204,1567579748,1568187255",
        "sid": "p8HXSTNo8h2dwU0kyZcoP2O2qdmBPMo1"
      },
      "arg": null,
      "args": "",
      "queryString": "",
      "header": {
        "Accept": [
          "text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3"
        ],
        "Accept-Encoding": [
          "gzip, deflate, br"
        ],
        "Accept-Language": [
          "en-US,en;q=0.9,zh-CN;q=0.8,zh-TW;q=0.7,zh;q=0.6,ja;q=0.5,pl;q=0.4,mt;q=0.3"
        ],
        "Cache-Control": [
          "max-age=0"
        ],
        "Connection": [
          "keep-alive"
        ],
        "Cookie": [
          "sid=p8HXSTNo8h2dwU0kyZcoP2O2qdmBPMo1; Hm_lvt_2259172a9054c42aae07421c8bbf3c84=1566973980,1567065204,1567579748,1568187255"
        ],
        "Sec-Fetch-Mode": [
          "navigate"
        ],
        "Sec-Fetch-Site": [
          "none"
        ],
        "Sec-Fetch-User": [
          "?1"
        ],
        "Upgrade-Insecure-Requests": [
          "1"
        ],
        "User-Agent": [
          "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/76.0.3809.132 Safari/537.36"
        ],
        "X-Forwarded-By": [
          "127.0.0.1:8882"
        ],
        "X-Forwarded-For": [
          "127.0.0.1"
        ],
        "X-Forwarded-Host": [
          "127.0.0.1:8882"
        ],
        "X-Forwarded-Proto": [
          "http"
        ],
        "X-Real-IP": [
          "127.0.0.1"
        ]
      },
      "serverName": "www.teaos.cn",
      "serverPort": 8882,
      "serverProtocol": "HTTP/1.1",
      "backendAddress": "127.0.0.1:9991",
      "fastcgiAddress": "",
      "requestData": "",
      "responseHeaderData": "SFRUUC8xLjEgMjAwIE9LDQpDb250ZW50LVR5cGU6IHRleHQvcGxhaW47IGNoYXJzZXQ9dXRmLTgNCkRhdGU6IFN1biwgMTUgU2VwIDIwMTkgMDc6NDk6NTYgR01UDQpIZWxsbzogV29ybGQNClgtQ2FjaGU6IEJZUEFTUw0KDQo=",
      "responseBodyData": "VGhpcyBpcyB0ZXN0IHNlcnZlcg==",
      "errors": null,
      "hasErrors": false,
      "extend": {
        "file": {
          "mimeType": "",
          "extension": "",
          "charset": ""
        },
        "client": {
          "os": {
            "family": "Mac OS X",
            "major": "10",
            "minor": "14",
            "patch": "6",
            "patchMinor": ""
          },
          "device": {
            "family": "Other",
            "brand": "",
            "model": ""
          },
          "browser": {
            "family": "Chrome",
            "major": "76",
            "minor": "0",
            "patch": "3809"
          }
        },
        "geo": {
          "region": "",
          "state": "",
          "city": "",
          "location": {
            "latitude": 0,
            "longitude": 0,
            "timeZone": "",
            "accuracyRadius": 0,
            "metroCode": 0
          }
        }
      },
      "attrs": {},
      "storageOnly": false,
      "storagePolicyIds": null
    },
    {
      "id": "5d7ded2609de0a0d51ef4d9f",
      "serverId": "JnZ03pbDebcOQ7h9",
      "backendId": "0biKxy56Y4sUoo9Z",
      "locationId": "",
      "fastcgiId": "",
      "rewriteId": "",
      "teaVersion": "0.1.7.2",
      "remoteAddr": "127.0.0.1",
      "remotePort": 0,
      "remoteUser": "",
      "requestURI": "/",
      "requestPath": "/",
      "apiPath": "",
      "apiStatus": "",
      "requestLength": 0,
      "requestTime": 0.000216082,
      "requestMethod": "GET",
      "requestFilename": "",
      "scheme": "http",
      "proto": "HTTP/1.1",
      "bytesSent": 19,
      "bodyBytesSent": 19,
      "status": 200,
      "statusMessage": "",
      "sentHeader": {
        "Content-Length": [
          "19"
        ],
        "Content-Type": [
          "text/plain; charset=utf-8"
        ],
        "Date": [
          "Sun, 15 Sep 2019 07:49:56 GMT"
        ],
        "Hello": [
          "World"
        ],
        "X-Cache": [
          "BYPASS"
        ]
      },
      "timeISO8601": "2019-09-15T15:49:56.982+08:00",
      "timeLocal": "15/Sep/2019:15:49:56 +0800",
      "msec": 1.568533796982034e+09,
      "timestamp": 1568533796,
      "host": "127.0.0.1:8882",
      "referer": "",
      "userAgent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/76.0.3809.132 Safari/537.36",
      "request": "GET / HTTP/1.1",
      "contentType": "",
      "cookie": {
        "Hm_lvt_2259172a9054c42aae07421c8bbf3c84": "1566973980,1567065204,1567579748,1568187255",
        "sid": "p8HXSTNo8h2dwU0kyZcoP2O2qdmBPMo1"
      },
      "arg": null,
      "args": "",
      "queryString": "",
      "header": {
        "Accept": [
          "text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3"
        ],
        "Accept-Encoding": [
          "gzip, deflate, br"
        ],
        "Accept-Language": [
          "en-US,en;q=0.9,zh-CN;q=0.8,zh-TW;q=0.7,zh;q=0.6,ja;q=0.5,pl;q=0.4,mt;q=0.3"
        ],
        "Cache-Control": [
          "max-age=0"
        ],
        "Connection": [
          "keep-alive"
        ],
        "Cookie": [
          "sid=p8HXSTNo8h2dwU0kyZcoP2O2qdmBPMo1; Hm_lvt_2259172a9054c42aae07421c8bbf3c84=1566973980,1567065204,1567579748,1568187255"
        ],
        "Sec-Fetch-Mode": [
          "navigate"
        ],
        "Sec-Fetch-Site": [
          "none"
        ],
        "Sec-Fetch-User": [
          "?1"
        ],
        "Upgrade-Insecure-Requests": [
          "1"
        ],
        "User-Agent": [
          "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/76.0.3809.132 Safari/537.36"
        ],
        "X-Forwarded-By": [
          "127.0.0.1:8882"
        ],
        "X-Forwarded-For": [
          "127.0.0.1"
        ],
        "X-Forwarded-Host": [
          "127.0.0.1:8882"
        ],
        "X-Forwarded-Proto": [
          "http"
        ],
        "X-Real-IP": [
          "127.0.0.1"
        ]
      },
      "serverName": "www.teaos.cn",
      "serverPort": 8882,
      "serverProtocol": "HTTP/1.1",
      "backendAddress": "127.0.0.1:9991",
      "fastcgiAddress": "",
      "requestData": "",
      "responseHeaderData": "SFRUUC8xLjEgMjAwIE9LDQpDb250ZW50LVR5cGU6IHRleHQvcGxhaW47IGNoYXJzZXQ9dXRmLTgNCkRhdGU6IFN1biwgMTUgU2VwIDIwMTkgMDc6NDk6NTYgR01UDQpIZWxsbzogV29ybGQNClgtQ2FjaGU6IEJZUEFTUw0KDQo=",
      "responseBodyData": "VGhpcyBpcyB0ZXN0IHNlcnZlcg==",
      "errors": null,
      "hasErrors": false,
      "extend": {
        "file": {
          "mimeType": "",
          "extension": "",
          "charset": ""
        },
        "client": {
          "os": {
            "family": "Mac OS X",
            "major": "10",
            "minor": "14",
            "patch": "6",
            "patchMinor": ""
          },
          "device": {
            "family": "Other",
            "brand": "",
            "model": ""
          },
          "browser": {
            "family": "Chrome",
            "major": "76",
            "minor": "0",
            "patch": "3809"
          }
        },
        "geo": {
          "region": "",
          "state": "",
          "city": "",
          "location": {
            "latitude": 0,
            "longitude": 0,
            "timeZone": "",
            "accuracyRadius": 0,
            "metroCode": 0
          }
        }
      },
      "attrs": {},
      "storageOnly": false,
      "storagePolicyIds": null
    }
  ]
}
~~~