# 冲突处理参数

| 参数名                 | 简要说明                                     |
| ------------------- | ---------------------------------------- |
| `conflict_target`   | 指定冲突检测的目标，可以推断唯一索引或直接命名约束。               |
| `conflict_action`   | 冲突时执行的动作：`DO NOTHING` 或 `DO UPDATE`。     |
| `index_column_name` | 用于推断仲裁索引的列名。                             |
| `index_expression`  | 用于推断索引表达式的表达式。                           |
| `collation`         | 指定索引推断时使用的排序规则。                          |
| `opclass`           | 指定索引推断时使用的操作符类。                          |
| `index_predicate`   | 用于推断部分唯一索引的谓词条件。                         |
| `constraint_name`   | 直接指定仲裁约束的名称。                             |
| `condition`         | `DO UPDATE` 中 `WHERE` 子句的条件，仅满足条件的行会被更新。 |
