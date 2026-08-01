# Valkey

一、状态管理

1. 当前登录session
2. 验证码
3. 限流计数
4. webhook去重
5. 在线状态
6. 热点bot配置

```
key:    tg_bot:secret:{token}
{
    bot_id
    status
}

// TTL
    1H
// session
    tma:user:{id}:session
// rate limit
    limit:user:{id}
// webhook dedup
    telegram:update:{bot_id}:{update_id}
    TTL 24h
```

二、bot

```
key: bot:1234
{
    id
    username
    status
    welcome_text
    promotion
}
```
