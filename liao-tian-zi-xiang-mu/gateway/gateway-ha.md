# gateway HA

一、

1. 使用msg-id去重
2. 消息有可能发到不同echo实例

二、trace-id

1. ha必须考虑trace-id
2. update中包含trace-id
3. 构建：bot-id:update-id
