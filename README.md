# EMQX kafka bridge

版本信息：
- erlang otp版本： otp-22.3
- 对应emqx-rel版本： v4.0.0

## 注意事项
- 在加载emqx_kafka_bridge插件前，必须提前在kafka集群中创建相关topic,目前有两个：
    - message_publish
    - 在etc/emqx_kafka_bridge.conf中配置的bridge.on_message_publish_topic
