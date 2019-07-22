# API描述
App列表，v0.1.6开始加入。

## API地址
~~~
/api/v1/agent/${agentId}/apps
~~~
其中：
* `${agentId}` - Agent ID

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
      "id": "system",
      "on": true,
      "tasks": [],
      "items": [
        {
          "on": true,
          "id": "cpu.usage",
          "name": "CPU使用量（%）",
          "sourceCode": "cpu",
          "sourceOptions": {
            "dataFormat": 3
          },
          "interval": "60s",
          "thresholds": [
            {
              "id": "ZNk2jFdj2w3x35YZ",
              "param": "${usage.avg}",
              "operator": "gte",
              "value": "80",
              "noticeLevel": 2,
              "noticeMessage": "",
              "actions": [],
              "maxFails": 0
            }
          ],
          "charts": [
            {
              "id": "cpu.chart1",
              "on": true,
              "name": "CPU使用量（%）",
              "description": "",
              "columns": 2,
              "type": "javascript",
              "options": {
                "code": "\nvar chart = new charts.LineChart();\nchart.max = 100;\n\nvar query = new values.Query();\nquery.limit(30)\nvar ones = query.desc().cache(60).findAll();\nones.reverse();\n\nvar lines = [];\n\n{\n\tvar line = new charts.Line();\n\tline.color = colors.ARRAY[0];\n\tline.isFilled = true;\n\tline.values = [];\n\tlines.push(line);\n}\n\nones.$each(function (k, v) {\n\tlines[0].values.push(v.value.usage.avg);\n\t\n\tvar minute = v.timeFormat.minute.substring(8);\n\tchart.labels.push(minute.substr(0, 2) + \":\" + minute.substr(2, 2));\n});\n\nchart.addLines(lines);\nchart.render();\n"
              },
              "requirements": []
            }
          ],
          "recoverSuccesses": 0
        },
        {
          "on": true,
          "id": "cpu.load",
          "name": "负载（Load）",
          "sourceCode": "load",
          "sourceOptions": {
            "dataFormat": 3
          },
          "interval": "60s",
          "thresholds": [
            {
              "id": "9lnnO7pwv21Tby9J",
              "param": "${load5}",
              "operator": "gte",
              "value": "10",
              "noticeLevel": 2,
              "noticeMessage": "",
              "actions": [],
              "maxFails": 0
            },
            {
              "id": "1AJS0sbwbfvdczkz",
              "param": "${load5}",
              "operator": "gte",
              "value": "20",
              "noticeLevel": 3,
              "noticeMessage": "",
              "actions": [],
              "maxFails": 0
            }
          ],
          "charts": [
            {
              "id": "cpu.load.chart1",
              "on": true,
              "name": "负载（Load）",
              "description": "",
              "columns": 2,
              "type": "javascript",
              "options": {
                "code": "\nvar chart = new charts.LineChart();\n\nvar query = new values.Query();\nquery.limit(30)\nvar ones = query.desc().cache(60).findAll();\nones.reverse();\n\nvar lines = [];\n\n{\n\tvar line = new charts.Line();\n\tline.name = \"1分钟\";\n\tline.color = colors.ARRAY[0];\n\tline.isFilled = true;\n\tline.values = [];\n\tlines.push(line);\n}\n\n{\n\tvar line = new charts.Line();\n\tline.name = \"5分钟\";\n\tline.color = colors.BROWN;\n\tline.isFilled = false;\n\tline.values = [];\n\tlines.push(line);\n}\n\n{\n\tvar line = new charts.Line();\n\tline.name = \"15分钟\";\n\tline.color = colors.RED;\n\tline.isFilled = false;\n\tline.values = [];\n\tlines.push(line);\n}\n\nvar maxValue = 1;\n\nones.$each(function (k, v) {\n\tlines[0].values.push(v.value.load1);\n\tlines[1].values.push(v.value.load5);\n\tlines[2].values.push(v.value.load15);\n\n\tif (v.value.load1 \u003e maxValue) {\n\t\tmaxValue = Math.ceil(v.value.load1 / 2) * 2;\n\t}\n\tif (v.value.load5 \u003e maxValue) {\n\t\tmaxValue = Math.ceil(v.value.load5 / 2) * 2;\n\t}\n\tif (v.value.load15 \u003e maxValue) {\n\t\tmaxValue = Math.ceil(v.value.load15 / 2) * 2;\n\t}\n\t\n\tvar minute = v.timeFormat.minute.substring(8);\n\tchart.labels.push(minute.substr(0, 2) + \":\" + minute.substr(2, 2));\n});\n\nchart.addLines(lines);\nchart.max = maxValue;\nchart.render();\n"
              },
              "requirements": []
            }
          ],
          "recoverSuccesses": 0
        },
        {
          "on": true,
          "id": "memory.usage",
          "name": "内存使用量",
          "sourceCode": "memory",
          "sourceOptions": {
            "dataFormat": 3
          },
          "interval": "60s",
          "thresholds": [
            {
              "id": "x1vB69pwJa6QB6MZ",
              "param": "${usage.virtualPercent}",
              "operator": "gte",
              "value": "80",
              "noticeLevel": 2,
              "noticeMessage": "",
              "actions": [],
              "maxFails": 0
            }
          ],
          "charts": [
            {
              "id": "memory.usage.chart1",
              "on": true,
              "name": "内存使用量（%）",
              "description": "",
              "columns": 2,
              "type": "javascript",
              "options": {
                "code": "\nvar chart = new charts.LineChart();\n\nvar query = new values.Query();\nquery.limit(30)\nvar ones = query.desc().cache(60).findAll();\nones.reverse();\n\nvar lines = [];\n\n{\n\tvar line = new charts.Line();\n\tline.color = colors.ARRAY[0];\n\tline.isFilled = true;\n\tline.values = [];\n\tlines.push(line);\n}\n\nones.$each(function (k, v) {\n\tlines[0].values.push(v.value.usage.virtualPercent);\n\n\tvar minute = v.timeFormat.minute.substring(8);\n\tchart.labels.push(minute.substr(0, 2) + \":\" + minute.substr(2, 2));\n});\n\nchart.addLines(lines);\nchart.max = 100;\nchart.render();\n"
              },
              "requirements": []
            },
            {
              "id": "memory.usage.chart2",
              "on": true,
              "name": "当前内存使用量",
              "description": "",
              "columns": 1,
              "type": "javascript",
              "options": {
                "code": "\nvar chart = new charts.StackBarChart();\n\nvar latest = new values.Query().latest(1);\nvar hasWarning = false;\nif (latest.length \u003e 0) {\n\thasWarning = (latest[0].value.usage.swapPercent \u003e 50) || (latest[0].value.usage.virtualPercent \u003e 80);\n\tchart.values = [ \n\t\t[latest[0].value.usage.swapUsed, latest[0].value.usage.swapTotal - latest[0].value.usage.swapUsed],\n\t\t[latest[0].value.usage.virtualUsed, latest[0].value.usage.virtualTotal - latest[0].value.usage.virtualUsed]\n\t];\n\tchart.labels = [ \"虚拟内存（\" +  (Math.round(latest[0].value.usage.swapUsed * 10) / 10) + \"G/\" + Math.round(latest[0].value.usage.swapTotal) + \"G\"  + \"）\", \"物理内存（\" + (Math.round(latest[0].value.usage.virtualUsed * 10) / 10)+ \"G/\" + Math.round(latest[0].value.usage.virtualTotal)  + \"G\"  + \"）\"];\n} else {\n\tchart.values = [ [0, 0], [0, 0] ];\n\tchart.labels = [ \"虚拟内存\", \"物理内存\" ];\n}\nif (hasWarning) {\n\tchart.colors = [ colors.RED, colors.GREEN ];\n} else {\n\tchart.colors = [ colors.BROWN, colors.GREEN ];\n}\nchart.render();\n"
              },
              "requirements": []
            }
          ],
          "recoverSuccesses": 0
        },
        {
          "on": true,
          "id": "clock",
          "name": "时钟",
          "sourceCode": "date",
          "sourceOptions": {
            "dataFormat": 3
          },
          "interval": "60s",
          "thresholds": [
            {
              "id": "zJy6cFB8vLGFtleW",
              "param": "new Date().getTime() / 1000 - ${timestamp}",
              "operator": "gte",
              "value": "300",
              "noticeLevel": 2,
              "noticeMessage": "主机时间出现很大偏差",
              "actions": [],
              "maxFails": 0
            }
          ],
          "charts": [
            {
              "id": "clock",
              "on": true,
              "name": "时钟",
              "description": "",
              "columns": 1,
              "type": "javascript",
              "options": {
                "code": "\nvar chart = new charts.Clock();\nvar latest = new values.Query().latest(1);\nif (latest.length \u003e 0) {\n\tchart.timestamp = parseInt(new Date().getTime() / 1000) - (latest[0].createdAt - latest[0].value.timestamp);\n}\nchart.render();\n"
              },
              "requirements": []
            }
          ],
          "recoverSuccesses": 0
        },
        {
          "on": true,
          "id": "network.usage",
          "name": "网络相关",
          "sourceCode": "network",
          "sourceOptions": {
            "dataFormat": 3
          },
          "interval": "60s",
          "thresholds": [
            {
              "id": "K2F7cmXDFRsa22Yf",
              "param": "${stat.avgSentBytes}",
              "operator": "gte",
              "value": "13107200",
              "noticeLevel": 2,
              "noticeMessage": "当前出口流量超过100MBit/s",
              "actions": [],
              "maxFails": 0
            }
          ],
          "charts": [
            {
              "id": "network.usage.received",
              "on": true,
              "name": "出口带宽（M/s）",
              "description": "",
              "columns": 2,
              "type": "javascript",
              "options": {
                "code": "\nvar chart = new charts.LineChart();\n\nvar line = new charts.Line();\nline.isFilled = true;\n\nvar ones = new values.Query().cache(60).latest(60);\nones.reverse();\nones.$each(function (k, v) {\n\tline.values.push(Math.round(v.value.stat.avgSentBytes / 1024 / 1024 * 100) / 100);\n\t\n\tvar minute = v.timeFormat.minute.substring(8);\n\tchart.labels.push(minute.substr(0, 2) + \":\" + minute.substr(2, 2));\n});\nvar maxValue = line.values.$max();\nif (maxValue \u003c 1) {\n\tchart.max = 1;\n} else if (maxValue \u003c 5) {\n\tchart.max = 5;\n} else if (maxValue \u003c 10) {\n\tchart.max = 10;\n}\n\nchart.addLine(line);\nchart.render();\n"
              },
              "requirements": []
            },
            {
              "id": "network.usage.sent",
              "on": true,
              "name": "入口带宽（M/s）",
              "description": "",
              "columns": 2,
              "type": "javascript",
              "options": {
                "code": "\nvar chart = new charts.LineChart();\n\nvar line = new charts.Line();\nline.isFilled = true;\n\nvar ones = new values.Query().cache(60).latest(60);\nones.reverse();\nones.$each(function (k, v) {\n\tline.values.push(Math.round(v.value.stat.avgReceivedBytes / 1024 / 1024 * 100) / 100);\n\t\n\tvar minute = v.timeFormat.minute.substring(8);\n\tchart.labels.push(minute.substr(0, 2) + \":\" + minute.substr(2, 2));\n});\nvar maxValue = line.values.$max();\nif (maxValue \u003c 1) {\n\tchart.max = 1;\n} else if (maxValue \u003c 5) {\n\tchart.max = 5;\n} else if (maxValue \u003c 10) {\n\tchart.max = 10;\n}\n\nchart.addLine(line);\nchart.render();\n"
              },
              "requirements": []
            }
          ],
          "recoverSuccesses": 0
        },
        {
          "on": true,
          "id": "disk.usage",
          "name": "文件系统",
          "sourceCode": "disk",
          "sourceOptions": {
            "dataFormat": 3
          },
          "interval": "120s",
          "thresholds": [
            {
              "id": "Xu6s8ZaZnKczGcxV",
              "param": "${partitions.$.percent}",
              "operator": "gt",
              "value": "80",
              "noticeLevel": 2,
              "noticeMessage": "${ROW.name}分区已使用80%",
              "actions": [],
              "maxFails": 0
            }
          ],
          "charts": [
            {
              "id": "disk.usage.chart1",
              "on": true,
              "name": "文件系统",
              "description": "",
              "columns": 2,
              "type": "javascript",
              "options": {
                "code": "\nvar chart = new charts.StackBarChart();\nchart.values = [];\nchart.labels = [];\n\nvar latest = new values.Query().cache(120).latest(1);\nif (latest.length \u003e 0) {\n\tvar partitions = latest[0].value.partitions;\n\tpartitions.$each(function (k, v) {\n\t\tchart.values.push([v.used, v.total - v.used]);\n\t\tchart.labels.push(v.name + \"（\" + (Math.round(v.used / 1024 / 1024 / 1024 * 100) / 100)+ \"G/\" + (Math.round(v.total / 1024 / 1024 / 1024 * 100) / 100) +\"G）\");\n\t});\n\n\tchart.options.height = partitions.length * 4;\n}\n\nchart.colors = [ colors.BROWN, colors.GREEN ];\nchart.render();\n"
              },
              "requirements": []
            }
          ],
          "recoverSuccesses": 0
        }
      ],
      "name": "系统",
      "isSharedWithGroup": false,
      "sharedAgentIds": [],
      "noticeSetting": {}
    }
  },
  {
    "config": {
      "id": "nXoJ3DK1idAXlE71",
      "on": true,
      "tasks": [],
      "items": [
        {
          "on": true,
          "id": "bvo64GUmYru1zFwx",
          "name": "进程",
          "sourceCode": "script",
          "sourceOptions": {
            "cwd": "",
            "dataFormat": 1,
            "env": [],
            "path": "",
            "script": "#!/usr/bin/env bash\r\n\r\nps ax|grep cloud|wc -l\r\nsleep 60\r\necho \"Hello\"\r\n",
            "scriptLang": "shell",
            "scriptType": "code"
          },
          "interval": "30s",
          "thresholds": [],
          "charts": [],
          "recoverSuccesses": 1
        },
        {
          "on": true,
          "id": "lvVHwRiBlUJHQa0D",
          "name": "1",
          "sourceCode": "script",
          "sourceOptions": {
            "cwd": "",
            "dataFormat": 1,
            "env": [],
            "path": "",
            "script": "#!/usr/bin/env bash\r\n\r\nps ax|grep cloud|wc -l\r\nsleep 60\r\necho \"Hello\"\r\n",
            "scriptLang": "shell",
            "scriptType": "code"
          },
          "interval": "10s",
          "thresholds": [],
          "charts": [],
          "recoverSuccesses": 1
        },
        {
          "on": true,
          "id": "gRyMPvs4q7Bj02hA",
          "name": "2",
          "sourceCode": "script",
          "sourceOptions": {
            "cwd": "",
            "dataFormat": 1,
            "env": [],
            "path": "",
            "script": "#!/usr/bin/env bash\r\n\r\nps ax|grep cloud|wc -l\r\nsleep 60\r\necho \"Hello\"\r\n",
            "scriptLang": "shell",
            "scriptType": "code"
          },
          "interval": "10s",
          "thresholds": [],
          "charts": [],
          "recoverSuccesses": 1
        },
        {
          "on": true,
          "id": "K7Kp6UexTmDjTWrD",
          "name": "3",
          "sourceCode": "script",
          "sourceOptions": {
            "cwd": "",
            "dataFormat": 1,
            "env": [],
            "path": "",
            "script": "#!/usr/bin/env bash\r\n\r\nps ax|grep cloud|wc -l\r\nsleep 60\r\necho \"Hello\"\r\n",
            "scriptLang": "shell",
            "scriptType": "code"
          },
          "interval": "30s",
          "thresholds": [],
          "charts": [],
          "recoverSuccesses": 1
        },
        {
          "on": true,
          "id": "NFP3w4oG3o37Z6rP",
          "name": "4",
          "sourceCode": "script",
          "sourceOptions": {
            "cwd": "",
            "dataFormat": 1,
            "env": [],
            "path": "",
            "script": "#!/usr/bin/env bash\r\n\r\nps ax|grep cloud|wc -l\r\nsleep 60\r\necho \"Hello\"\r\n",
            "scriptLang": "shell",
            "scriptType": "code"
          },
          "interval": "10s",
          "thresholds": [],
          "charts": [],
          "recoverSuccesses": 1
        },
        {
          "on": true,
          "id": "lNO8XtO3sdsOra7w",
          "name": "5",
          "sourceCode": "script",
          "sourceOptions": {
            "cwd": "",
            "dataFormat": 1,
            "env": [],
            "path": "",
            "script": "#!/usr/bin/env bash\r\n\r\nps ax|grep cloud|wc -l\r\nsleep 60\r\necho \"Hello\"\r\n",
            "scriptLang": "shell",
            "scriptType": "code"
          },
          "interval": "10s",
          "thresholds": [],
          "charts": [],
          "recoverSuccesses": 1
        }
      ],
      "name": "测试啊",
      "isSharedWithGroup": false,
      "sharedAgentIds": [],
      "noticeSetting": {}
    }
  },
  {
    "config": {
      "id": "H5xSwPOXlRkTgEQ6",
      "on": true,
      "tasks": [],
      "items": [
        {
          "on": true,
          "id": "oVq0Nx7bYB7lwbrN",
          "name": "postgres",
          "sourceCode": "postgre.sql",
          "sourceOptions": {
            "addr": "127.0.0.1:5432",
            "dataFormat": 1,
            "databaseName": "postgres",
            "password": "123456",
            "sql": "SELECT * FROM settings",
            "timeoutSeconds": 10,
            "username": "postgres"
          },
          "interval": "30s",
          "thresholds": [],
          "charts": [],
          "recoverSuccesses": 1
        }
      ],
      "name": "postgres",
      "isSharedWithGroup": true,
      "sharedAgentIds": [],
      "noticeSetting": {}
    }
  }
]
~~~