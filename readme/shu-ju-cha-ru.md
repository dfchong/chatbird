# 数据插入

```
// 1. 插入一条文档
INSERT INTO user_profiles (data) VALUES (
    '{
        "username": "zhangsan",
        "email": "zhangsan@example.com",
        "age": 28,
        "roles": ["admin", "developer"],
        "settings“: {
            "theme": "dark",
            "notifications": true
        }
    }'
);
```
