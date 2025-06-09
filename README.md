# RabbitMQ Plugin for Dify

**Author:** 294033186  
**Version:** 0.0.1  
**Type:** tool  

## Description

The **RabbitMQ Plugin** is a plugin for the Dify platform that provides integration with the RabbitMQ message queue system. With this plugin, you can send messages to a RabbitMQ server and consume messages from a RabbitMQ queue within your Dify applications.

## Features

This plugin offers two main functions:

1. **Send Message (`rabbit_send_plugin`)**:
   - Send a message to a specified RabbitMQ exchange
   - Support for specifying a routing key
   - Custom message body support

2. **Consume Message (`rabbit_consumer_plugin`)**:
   - Consume messages from a specified RabbitMQ queue
   - Support for limiting the number of messages consumed
   - Returns the consumed message content

## Requirements

- Dify platform version >= 1.4.1
- An accessible RabbitMQ server

## Configuration Parameters

When installing the plugin, provide the following RabbitMQ connection information:

- **rabbitmq addresses**: RabbitMQ server address in the format `host:port`, default is `127.0.0.1:5672`
- **username**: RabbitMQ username
- **password**: RabbitMQ password
- **vhost**: RabbitMQ virtual host, default is `/`

## Usage Examples

### Sending a Message

```
// Send a message to the exchange named "my_exchange" with routing key "my_routing_key"
{
  "Exchange": "my_exchange",
  "RoutingKey": "my_routing_key",
  "Message": "Hello, RabbitMQ!"
}
```

### Consuming Messages

```
// Consume 5 messages from the queue named "my_queue"
{
  "Queue": "my_queue",
  "Count": 5
}
```

## Usage Guide

### Enter Authentication Information
<img width="1439" alt="image" src="https://github.com/user-attachments/assets/9386ad80-5b3e-4704-9686-10bedd51ba9e" />

### After Authentication, You Will See an "Authorized" Status
<img width="1435" alt="image" src="https://github.com/user-attachments/assets/38a61120-f7c0-443d-a8c6-62e5e8478098" />

### Send Mode: Configure the Target Exchange and Routing Key
<img width="1439" alt="image" src="https://github.com/user-attachments/assets/46680b8c-9f05-4dee-a451-1f30146f91b6" />

### Consume Mode: Configure the Queue and the Number of Messages to Consume
<img width="1432" alt="image" src="https://github.com/user-attachments/assets/390c7f9c-f58b-44ed-af9c-4b1d69a285ec" />

### Execution Results

#### Sending Messages
<img width="1439" alt="image" src="https://github.com/user-attachments/assets/54d72104-c54a-4ded-8fbd-2321f1a2b68c" />

#### Consuming Messages
<img width="1431" alt="image" src="https://github.com/user-attachments/assets/af923ffc-06b8-4f51-af34-6c7df6f2a696" />


## Notes

1. Ensure that the RabbitMQ server is properly configured and accessible before use.
2. The exchange and queue must be created in RabbitMQ in advance.
3. When consuming messages, if the number of available messages is less than the requested count, only the available messages will be returned.

## Troubleshooting

If you encounter connection issues, please check:

1. Whether the RabbitMQ server is running properly
2. Whether the provided connection information (address, username, password, virtual host) is correct
3. Whether the network connection is working properly
4. Whether the firewall allows access to the relevant ports

## Support

If you have any questions or need help, please contact us via:

- GitHub Repository: [https://github.com/294033186/rabbitmq-plugin](https://github.com/294033186/rabbitmq-plugin)
- Submit an Issue: [https://github.com/294033186/rabbitmq-plugin/issues](https://github.com/294033186/rabbitmq-plugin/issues)

## License

[MIT License](LICENSE)

