# RabbitMQ Plugin for Dify

**Author:** zxp  
**Version:** 0.0.1  
**Type:** tool  

## 描述

RabbitMQ Plugin 是一个用于 Dify 平台的插件，提供与 RabbitMQ 消息队列系统交互的能力。通过此插件，您可以在 Dify 应用中发送消息到 RabbitMQ 服务器，以及从 RabbitMQ 队列中消费消息。

## 功能

该插件提供两个主要功能：

1. **发送消息 (rabbit_send_plugin)**：
   - 向指定的 RabbitMQ 交换机发送消息
   - 支持指定路由键
   - 支持自定义消息内容

2. **消费消息 (rabbit_consumer_plugin)**：
   - 从指定的 RabbitMQ 队列中消费消息
   - 支持指定消费消息的数量
   - 返回消费的消息内容

## 安装要求

- Dify 平台版本 >= 1.4.1
- 可访问的 RabbitMQ 服务器

## 配置参数

安装插件时，需要提供以下 RabbitMQ 连接信息：

- **rabbitmq addresses**：RabbitMQ 服务器地址，格式为 `host:port`，默认为 `127.0.0.1:5672`
- **username**：RabbitMQ 用户名
- **password**：RabbitMQ 密码
- **vhost**：RabbitMQ 虚拟主机，默认为 `/`

## 使用示例

### 发送消息

```
// 向名为 "my_exchange" 的交换机发送消息，路由键为 "my_routing_key"
{
  "Exchange": "my_exchange",
  "RoutingKey": "my_routing_key",
  "Message": "Hello, RabbitMQ!"
}
```

### 消费消息

```
// 从名为 "my_queue" 的队列中消费 5 条消息
{
  "Queue": "my_queue",
  "Count": 5
}
```

## 注意事项

1. 使用前请确保 RabbitMQ 服务器已正确配置并可访问
2. 交换机和队列需要提前在 RabbitMQ 中创建
3. 消费消息时，如果队列中的消息数量少于请求的数量，将只返回可用的消息

## 故障排除

如果遇到连接问题，请检查：

1. RabbitMQ 服务器是否正常运行
2. 提供的连接信息（地址、用户名、密码、虚拟主机）是否正确
3. 网络连接是否正常
4. 防火墙设置是否允许相关端口的访问

## 支持

如有问题或需要帮助，请通过以下方式联系：

- GitHub 仓库：https://github.com/294033186/rabbitmq-plugin
- 提交 Issue：https://github.com/294033186/rabbitmq-plugin/issues

## 许可证

[MIT License](LICENSE)

