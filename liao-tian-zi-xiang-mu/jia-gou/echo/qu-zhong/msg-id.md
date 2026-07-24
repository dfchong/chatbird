# msg-id

一、

1. header: Nats-Msg-Id
2. jestream会保留msg-id一段时间 （时间窗可控）

二、如何设计&#x20;

1. 不要直接使用update-id，因为有很多bot，不同bot可能冲突
2. 正确：bot\_id:update\_id&#x20;
3. 推荐：telegram:bot\_id:update\_id

三、msg-id不是最终防重

1. 只保证消息进入stream时不重复
2. 不保证消费者业务执行一次
   1. consumer消费失败
   2. 没有发回ack
   3. 消息重投
