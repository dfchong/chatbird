# 索引优化

1. 解决 NoSQL查询慢的关键
2. 直接查询会引发全表扫描
3. GIN（Generalized Inverted Index）

```
// 1. 默认gin索引
    CREATE INDEX idx_users_profile ON users USING gin (profile)
        // 支持：@> ? ?| ?&
        // 灵活，但索引体积较大
// 2. 路径GIN索引
    CREATE INDEX idx_users_profile_path ON users USING gin (profile jsonb_path_ops)
        // 仅支持：@>
        // 索引体积小，查询效率高
// 3. 表达式B-Tree索引 （只关心JSON内部，不需要全文索引）
    CREATE INDEX idx_users_email ON users ((profile->>'email'))
        // 适用于等值匹配（where profile->>'email' = 'a@b.com'）

```
