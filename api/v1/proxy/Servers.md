# API描述
代理服务列表，v0.1.6开始加入。

## API地址
~~~
/api/v1/proxy/servers
~~~

## 请求方法
~~~
GET
~~~

## 请求参数
无

## 返回结果示例
~~~json
[
  {
    "config": {
      "headers": [
        {
          "on": true,
          "id": "fA2fOzvKnIjdqdk8",
          "name": "X-Cache",
          "value": "${cache.status}",
          "always": true,
          "status": []
        }
      ],
      "ignoreHeaders": [],
      "requestHeaders": [],
      "fastcgi": [],
      "rewrite": [],
      "backends": [
        {
          "headers": [],
          "ignoreHeaders": [],
          "requestHeaders": [],
          "on": true,
          "id": "0biKxy56Y4sUoo9Z",
          "code": "",
          "address": "127.0.0.1:9991",
          "scheme": "http",
          "weight": 10,
          "isBackup": false,
          "failTimeout": "0s",
          "readTimeout": "0s",
          "maxFails": 5,
          "currentFails": 0,
          "maxConns": 0,
          "currentConns": 0,
          "isDown": false,
          "downTime": "0001-01-01T00:00:00Z",
          "requestGroupIds": [
            "default"
          ],
          "requestURI": "${requestURI}",
          "responseHeaders": [],
          "host": "shop.balefm.cn",
          "checkURL": "http://www.facebook.com",
          "checkInterval": 5
        }
      ],
      "scheduling": null,
      "on": true,
      "id": "JnZ03pbDebcOQ7h9",
      "teaVersion": "0.1.6",
      "description": "负载均衡",
      "name": [
        "teaos.cn",
        "www.teaos.cn"
      ],
      "http": true,
      "redirectToHttps": false,
      "isDefault": false,
      "listen": [
        "127.0.0.1:8882"
      ],
      "root": "",
      "index": [
        "index.html",
        "index.htm",
        "index.php"
      ],
      "charset": "utf-8",
      "locations": [
        {
          "headers": [],
          "ignoreHeaders": [],
          "requestHeaders": [],
          "fastcgi": [],
          "rewrite": [],
          "backends": [],
          "scheduling": null,
          "on": true,
          "id": "iH33hcpIA7ShibqW",
          "name": "",
          "pattern": "~ \\.(png|jpg|jpeg)",
          "async": false,
          "notify": [],
          "logOnly": false,
          "root": "",
          "index": [],
          "charset": "",
          "maxBodySize": "0m",
          "gzipLevel": -1,
          "gzipMinLength": "0k",
          "accessPolicy": null,
          "redirectToHttps": false,
          "accessLog": [],
          "disableAccessLog": false,
          "accessLogFields": [],
          "disableStat": false,
          "allow": [],
          "deny": [],
          "proxy": "",
          "cachePolicy": "cache.policy.TsLoVtMWytLayYXZ.conf",
          "cacheOn": true,
          "wafOn": true,
          "wafId": "",
          "websocket": null,
          "cond": []
        },
        {
          "headers": [],
          "ignoreHeaders": [],
          "requestHeaders": [],
          "fastcgi": [],
          "rewrite": [
            {
              "headers": [],
              "ignoreHeaders": [],
              "requestHeaders": [],
              "on": true,
              "id": "XNPQjUb1lpL89oAb",
              "cond": [
                {
                  "id": "i0hmlJPF3ofeCGvu",
                  "param": "${remotePort}",
                  "operator": "eq",
                  "value": "80"
                },
                {
                  "id": "YMtKz4wAdAhxhWyA",
                  "param": "${remoteAddr}",
                  "operator": "eq",
                  "value": "127.0.0.1"
                }
              ],
              "pattern": ".+",
              "replace": "${0}",
              "flags": [
                "p"
              ],
              "flagOptions": {}
            }
          ],
          "backends": [],
          "scheduling": null,
          "on": true,
          "id": "bYTwBU5vYJzZ1PTl",
          "name": "",
          "pattern": "/hello",
          "async": false,
          "notify": [],
          "logOnly": false,
          "root": "",
          "index": [],
          "charset": "",
          "maxBodySize": "0m",
          "gzipLevel": -1,
          "gzipMinLength": "0k",
          "accessPolicy": null,
          "redirectToHttps": false,
          "accessLog": [],
          "disableAccessLog": false,
          "accessLogFields": [],
          "disableStat": false,
          "allow": [],
          "deny": [],
          "proxy": "",
          "cachePolicy": "",
          "cacheOn": true,
          "wafOn": true,
          "wafId": "",
          "websocket": null,
          "cond": [
            {
              "id": "59zAVkjrGssaAbOD",
              "param": "${requestMethod}",
              "operator": "eq",
              "value": "POST"
            }
          ]
        }
      ],
      "maxBodySize": "0m",
      "gzipLevel": 0,
      "gzipMinLength": "0k",
      "accessLog": [
        {
          "id": "J11iF74geZqHYqQC",
          "on": false,
          "fields": [
            1,
            2,
            3,
            4,
            5,
            6,
            7
          ],
          "status1": true,
          "status2": true,
          "status3": true,
          "status4": true,
          "status5": true,
          "storageOnly": false,
          "storagePolicies": []
        }
      ],
      "disableAccessLog": false,
      "accessLogFields": [],
      "disableStat": true,
      "ssl": {
        "on": true,
        "certificate": "",
        "certificateKey": "",
        "certs": [
          {
            "id": "LFAxwgzPTHH3RS82",
            "on": true,
            "description": "",
            "certFile": "ssl.IEXx4ojsmIhPURQ1.pem",
            "keyFile": "ssl.xPyRepECWyTpMTD0.key",
            "isLocal": false,
            "taskId": ""
          }
        ],
        "certTasks": [],
        "listen": [
          "0.0.0.0:8890"
        ],
        "minVersion": "TLS 1.0",
        "cipherSuites": [],
        "hsts": {
          "on": false,
          "maxAge": 31536000,
          "includeSubDomains": true,
          "preload": false,
          "domains": []
        }
      },
      "tcp": null,
      "allow": [],
      "deny": [],
      "filename": "server.JnZ03pbDebcOQ7h9.proxy.conf",
      "proxy": "",
      "cachePolicy": "",
      "cacheOn": true,
      "wafOn": true,
      "wafId": "",
      "api": {
        "on": false,
        "files": [],
        "groups": [],
        "versions": [],
        "testPlans": [],
        "status": [],
        "statusScriptOn": false,
        "statusScript": "",
        "mockOn": false,
        "consumerFiles": []
      },
      "realtimeBoard": {
        "charts": [
          {
            "widgetId": "teaweb.proxy_status",
            "chartId": "kTVuOEBm605H3AJS"
          },
          {
            "widgetId": "teaweb.locations",
            "chartId": "cyZsvwR66oxcVpvj"
          },
          {
            "widgetId": "teaweb.bandwidth_realtime",
            "chartId": "hiAUsteL1V6LG8zD"
          },
          {
            "widgetId": "teaweb.request_realtime",
            "chartId": "APvSaVEoQ7VUvX4a"
          },
          {
            "widgetId": "teaweb.request_time",
            "chartId": "g8SrxuMYwwhxNWwk"
          },
          {
            "widgetId": "teaweb.status_stat",
            "chartId": "xnUsgQMSjWZ9MN7g"
          },
          {
            "widgetId": "teaweb.latest_errors",
            "chartId": "RUCF1EbF4FpPMHpN"
          }
        ]
      },
      "statBoard": {
        "charts": [
          {
            "widgetId": "teaweb.request_stat",
            "chartId": "QdC9mdfECEqdKllp"
          },
          {
            "widgetId": "teaweb.url_rank",
            "chartId": "3TLvbynJiU6Ik5Yh"
          },
          {
            "widgetId": "teaweb.cost_rank",
            "chartId": "U79hACpwPmMtmEgu"
          },
          {
            "widgetId": "teaweb.os_rank",
            "chartId": "rJLuNQm6UeGJbyz6"
          },
          {
            "widgetId": "teaweb.browser_rank",
            "chartId": "2yS1FKYOv0nIMc4I"
          },
          {
            "widgetId": "teaweb.region_rank",
            "chartId": "nDx94UkqwzrdaNg1"
          },
          {
            "widgetId": "teaweb.province_rank",
            "chartId": "chtZBWnb955NCre7"
          }
        ]
      },
      "cacheStatic": false,
      "requestGroups": [
        {
          "backends": [
            {
              "headers": [],
              "ignoreHeaders": [],
              "requestHeaders": [],
              "on": true,
              "id": "0biKxy56Y4sUoo9Z",
              "code": "",
              "address": "127.0.0.1:9991",
              "scheme": "http",
              "weight": 10,
              "isBackup": false,
              "failTimeout": "0s",
              "readTimeout": "0s",
              "maxFails": 5,
              "currentFails": 0,
              "maxConns": 0,
              "currentConns": 0,
              "isDown": false,
              "downTime": "0001-01-01T00:00:00Z",
              "requestGroupIds": [
                "default"
              ],
              "requestURI": "${requestURI}",
              "responseHeaders": [],
              "host": "shop.balefm.cn",
              "checkURL": "http://www.facebook.com",
              "checkInterval": 5
            }
          ],
          "scheduling": null,
          "id": "default",
          "name": "默认分组",
          "conds": [],
          "ipRanges": [],
          "isDefault": true,
          "requestHeaders": [],
          "responseHeaders": []
        }
      ],
      "pages": [],
      "shutdownPageOn": false,
      "shutdownPage": "",
      "version": 98,
      "tunnel": null
    }
  },
  ...
]
~~~
