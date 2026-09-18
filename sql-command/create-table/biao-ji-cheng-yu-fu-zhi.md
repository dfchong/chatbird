# 表继承与复制

| 参数                                      | 简要说明                                                                                                                                  |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `INHERITS ( parent_table ... )`         | 从父表继承所有列，建立持久父子关系，父表结构变更会传播到子表。                                                                                                       |
| `LIKE source_table [ like_option ... ]` | 复制源表的列名、数据类型和 NOT NULL 约束，但创建后两表完全解耦。                                                                                                 |
| `like_option`                           | 控制复制哪些额外属性：`INCLUDING COMMENTS`、`COMPRESSION`、`CONSTRAINTS`、`DEFAULTS`、`GENERATED`、`IDENTITY`、`INDEXES`、`STATISTICS`、`STORAGE`、`ALL`。 |

