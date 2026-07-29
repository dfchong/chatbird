# 创建

```
// 1. ID主键
    CREATE TABLE user-profiles (
        id BIGSERIAL PRIMARY KEY,
        data JSONB NOT NULL
    );
// 2. 使用UUID主键
    CREATE TABLE user-profiles )
        id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
        data JSONB NOT NULL
    );
```

