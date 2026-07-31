# 一个用户只能注册一个bot

一、数据库约束

1. owner\_id 唯一

二、为什么不把owner\_id设计成主键

1. owner\_id: 业务唯一标识
2. id: 数据库内部主键

三、主键最好是数据库内部概念

1. 主键承担：
   1. 行唯一标识
   2. 外键关联
   3. 索引聚集
   4. 数据迁移稳定性
2. owner\_id是外部系统字段
   1. 第三方规则可能变化
3. 多平台帐号会破坏设计
   1. telegram
   2. discord
   3. wechat
4. 主键自增 bigint 性能更好
   1. id bigint generated always as identity primary key
   2. owner\_id: 随机分布

四、结论：

1. 用数据库生成的主键
2. 项目扩展空间大
