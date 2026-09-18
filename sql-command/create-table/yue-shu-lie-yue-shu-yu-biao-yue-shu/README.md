# 约束（列约束与表约束）

| 参数                                                              | 简要说明                                                                   |
| --------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `CONSTRAINT constraint_name`                                    | 为约束命名，便于错误信息识别。                                                        |
| `NOT NULL [ NO INHERIT ]`                                       | 列不允许为空；`NO INHERIT` 表示不传播到子表。                                          |
| `NULL`                                                          | 列允许为空（默认），仅为兼容性提供。                                                     |
| `CHECK ( expression ) [ NO INHERIT ]`                           | 检查约束，表达式为真或未知时通过。                                                      |
| `DEFAULT default_expr`                                          | 为列设置默认值。                                                               |
| `GENERATED ALWAYS AS ( generation_expr ) [ STORED \| VIRTUAL ]` | 创建生成列，`STORED` 写入时计算并存储，`VIRTUAL` 读取时计算（默认）。                           |
| `GENERATED { ALWAYS \| BY DEFAULT } AS IDENTITY`                | 创建标识列，自动从序列取值；`ALWAYS` 时用户插入需 `OVERRIDING SYSTEM VALUE`。               |
| `UNIQUE [ NULLS [ NOT ] DISTINCT ]`                             | 唯一约束，可指定 `NULLS NOT DISTINCT` 使空值也参与唯一性判断。                             |
| `PRIMARY KEY`                                                   | 主键约束，等价于 `UNIQUE` + `NOT NULL`，每表只能有一个。                                |
| `REFERENCES reftable ...`                                       | 外键约束，引用另一表的主键或唯一约束。                                                    |
| `EXCLUDE [ USING index_method ]`                                | 排除约束，保证任意两行在指定运算符下不会全部为真（如防止圆重叠）。                                      |
| `DEFERRABLE` / `NOT DEFERRABLE`                                 | 控制约束是否可延迟到事务结束时检查（仅 `UNIQUE`、`PRIMARY KEY`、`EXCLUDE`、`REFERENCES` 支持）。 |
| `INITIALLY IMMEDIATE` / `INITIALLY DEFERRED`                    | 设置可延迟约束的默认检查时机。                                                        |
| `ENFORCED` / `NOT ENFORCED`                                     | 是否由数据库强制检查约束（仅 `CHECK` 和 `FOREIGN KEY` 支持 `NOT ENFORCED`）。             |
