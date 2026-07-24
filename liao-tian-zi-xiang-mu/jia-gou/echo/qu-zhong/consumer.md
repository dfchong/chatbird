# consumer

1. comsumer处理消息时，一定要使用msg-id
2. 要有ack
3. 使用设计的函数防止重复操作
4. msg-id：唯一索引

```
if duplicate(err){    //发生重复操作错误
    msg.Ack()         // ack回复处理完成
    return
}
```
