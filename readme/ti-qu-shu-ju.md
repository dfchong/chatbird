# 提取数据

1. 表：order
2. 字段：data
   1. 类型: JSONB
   2. 值：

```
{
    "user": {
        "id": 101,
        "name": "Alice"
    },
    "tags": [
        "vip",
        "active"
    ]
}
```

```
SELECT data->'user' FROM order
SELECT data->'user'->>'name' FROM orders

SELECT data->'Tags'->>0 FROM orders
SELECT data#>>'{user, name}' FROM orders
```
