# 存储与访问方法

| 参数                                                   | 简要说明                                                  |
| ---------------------------------------------------- | ----------------------------------------------------- |
| `USING method`                                       | 指定表的访问方法（如 `heap`），需为 `TABLE` 类型的访问方法。                |
| `WITH ( storage_parameter ... )`                     | 设置表的存储参数（如 `fillfactor`、`autovacuum_enabled` 等），详见后文。 |
| `WITHOUT OIDS`                                       | 向后兼容语法，声明表不含 OID（新版本已不支持 `WITH OIDS`）。                |
| `TABLESPACE tablespace_name`                         | 指定表所在的表空间。                                            |
| `ON COMMIT { PRESERVE ROWS \| DELETE ROWS \| DROP }` | 控制临时表在事务提交时的行为：保留行、删除行或删除表。                           |
