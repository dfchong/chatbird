# Outbox Pattern

一、整体架构

```
1. 用户提交
2. 数据库事务
    bot_registry insert
    bot_event_outbox insert
    提交事务
3. select 未发布事件
4. 如果有：publish -> jetstream
5. published = true UPDATE (bot_event_outbox)

```
