# session

一、

1. redis
2. 保存短生命周期
3. 临时状态
4. 让bot能够理解用户当前正在进行什么操作？
5. 类似于“上下文记忆”

二、为什么tg-bot需要session

1. update本身是无状态的
2. 没有用户端操作信息

三、session本质

1. user\_id
2. current\_status
3. step
4. temporary\_data
5. expire\_time

```
telegram:session:123456
{
    "state": "ORDER_CREATE",
    "step": "SELECT_PLAN",
    "data": {
        "plan_id": null
    }
}
```

四、场景一：多步聚流程，购买流程

```
// 第一步：用户购买 
    用户：/buy
    bot: 请选择套餐
    session: {
        state: "buy",
        step: "select_plan"
    }
// 第二步：用户选择 3
    用户：3
    程序：读取session
    修改session: {
        step: payment
        plan_id = 3
        }
    
```

五、场景二：客服转接状态

```
客户->telegram -> bot -> 管理平台 -> 管理员
// 客户属于哪个客服的会话
chat_session:bot1:user123    // bot1与user123的会话
{
    admin_id: 888,
    status: "connected"
    last_message: "xxx",
}
用户123发：hello
查询chat_session -> 找到管理员888 -> 转发
```

六、场景三：防止重复提交

```
// 用户点击购买 
// bot重复发送 update
session:{
    processing = true
}
```

七、场景四：限流

```
// 用户 1秒内发送100条消息
session:
ratelimit:user.12345
count = 20
expire = 1s
```

八、与数据库的区别

1. 数据库：长期数据，永久
2. session:&#x20;
   1. 临时状态&#x20;
   2. 生命周期 秒

九、多bot平台中的设计

```
bot_session:{bot_id}:{user_id}
{
    "state": "chat",
    "admin_id": 888,
    "last_update": 1234
}
TTL : 3600
```

十、session数据结构建议

```
bot_session:{bot_id}:{user_id}
{
    "state": "chat",
    "step": "wati_reply",
    "customer":{
        "id": 888
    }
    "conversation_id": "abc123",
    "admin_id": 999,
    "last_update_id": 1223,
    "updated_at": 12453
}
TTL: 30m
```

十一、不建议放在session里的内容：

1. 用户资料
2. 聊天记录
3. bot配置

十二、什么是session

1. bot的短期记忆
2. 保存用户当前对话上下文
