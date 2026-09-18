# 创建、修改和删除数据库对象

| 命令             | 核心用途                                                                                     |
| -------------- | ---------------------------------------------------------------------------------------- |
| **CREATE** ... | 创建新对象，如 `CREATE TABLE`、`CREATE INDEX`、`CREATE VIEW`、`CREATE FUNCTION`、`CREATE SCHEMA` 等。 |
| **ALTER** ...  | 修改现有对象的定义，如 `ALTER TABLE` 添加列、`ALTER INDEX` 重命名索引。                                       |
| **DROP** ...   | 删除对象，如 `DROP TABLE`、`DROP FUNCTION`、`DROP INDEX`。                                        |
| **TRUNCATE**   | 快速清空表中的所有行，比 `DELETE` 更高效且不记录单行删除操作。                                                     |
| **COMMENT**    | 为数据库对象添加注释说明。                                                                            |
