# 架构

```
telegram -> cf tunnel -> echo -> telebot -> nats -> bot_worker + chat_worker
```

1. telebot
   1. update解析
   2. 提供handler
2. echo
   1.
3. bot worker
   1. 命令处理（/start）
   2. 自动回复
   3. tma入品
   4. 风控
4. chat worker
   1.
