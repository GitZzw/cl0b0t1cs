## consul
>> Consul是一个服务网格（微服务间的 TCP/IP，负责服务之间的网络调用、限流、熔断和监控）解决方案，它是一个一个分布式的，高度可用的系统，而且开发使用都很简便。它提供了一个功能齐全的控制平面，主要特点是：服务发现、健康检查、键值存储、安全服务通信、多数据中心。

>> 官方教程 https://learn.hashicorp.com/tutorials/consul/get-started?in=consul/getting-started

>> consul API in github https://github.com/hashicorp/consul/tree/master/api

>> consul API in go https://pkg.go.dev/github.com/hashicorp/consul/api


>> consul demo https://studygolang.com/articles/13293


>> consul with docker https://learn.hashicorp.com/tutorials/consul/docker-container-agents

`consul agent -dev`
>> 在开发模式下启动Consul代理，该代理程序正在作为服务器运行，并具有领导地位。本地代理已被标记为数据中心的正常成员


`consul members`
>> 检查Consul数据中心的成员身份，输出列出了数据中心中的代理

`consul leave`
>> 停止代理

### 定义服务
```
echo '{
  "service": {
    "name": "web",
    "tags": [
      "rails"
    ],
    "port": 80
  }
}' > ./consul.d/web.json
```

`consul agent -dev -enable-script-checks -config-dir ./consul.d`

`consul agent -dev -enable-script-checks -config-file .\consul.d\web.json`

### 查询服务
>> 代理将服务添加到Consul的服务目录后，您可以使用DNS接口或HTTP API对其进行查询。

HTTP API

`curl http://localhost:8500/v1/catalog/service/web `
