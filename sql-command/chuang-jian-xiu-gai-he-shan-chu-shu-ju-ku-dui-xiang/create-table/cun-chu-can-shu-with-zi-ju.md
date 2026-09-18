# 存储参数（WITH 子句）

| 参数                            | 简要说明                                               |
| ----------------------------- | -------------------------------------------------- |
| `fillfactor`                  | 表页填充百分比（10-100），为更新预留空间。                           |
| `toast_tuple_target`          | 触发 TOAST 的元组长度阈值。                                  |
| `parallel_workers`            | 并行扫描的工作进程数。                                        |
| `autovacuum_enabled`          | 是否启用自动清理。                                          |
| `vacuum_index_cleanup`        | 控制 VACUUM 时的索引清理行为。                                |
| `vacuum_truncate`             | 控制 VACUUM 是否截断末尾空页。                                |
| `autovacuum_*`                | 一系列自动清理阈值和比例因子（如 `autovacuum_vacuum_threshold` 等）。 |
| `log_autovacuum_min_duration` | 记录自动清理日志的最短耗时。                                     |
| `user_catalog_table`          | 声明为逻辑复制用的额外目录表。                                    |
