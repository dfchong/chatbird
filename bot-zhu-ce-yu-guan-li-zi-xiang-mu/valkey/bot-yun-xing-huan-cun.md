# bot运行缓存

```
key: bot:runtime:{bot_id}
value: {
    bot_id
    owner_id
    username
    status
    promotion_enabled
    welcome_text
}
TTL: 3600
```

1. 用于 webhook gateway 查询
