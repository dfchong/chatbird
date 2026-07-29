# 包含与存在查询

```
// 1. 包含操作符: @>
    SELECT * FROM users WHERE profile @> '{"role": "admin"}'
// 2. 键存在判断: ?
    SELECT * FROM users WHERE profile ? 'phone'
// 3. 多键存在判断: ?| / ?&
    SELECT * FROM users WHERE profile ?| array['email', 'phone']
```
