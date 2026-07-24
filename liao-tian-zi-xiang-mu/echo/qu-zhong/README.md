# 去重

一、产生重复请求

1. telegarm webhook 重试导致重复update
2. echo多实例并发处理重复请求
3. nats/jetstream投递导致重复消费
4. 业务处理失败后的重放同一个bot ，update\_id唯一
