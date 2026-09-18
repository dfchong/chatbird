---
description: 仅在超过8k时考虑配置
---

# STORAGE

1. 超长属性存储技术
2. 数据超过8k：
   1. 优先压缩：导找设置了EXTENDED MAIN
   2. 移至页外TOAST表
   3. 处理EXTERNAL：如果依然超大，会将external列移入TOAST表
3. 手动指定该列如何压缩或存放页外 （什么是存放页外）
4. 建议：不显示声明STORAGE，由PG自动按EXTENDED处理 （什么是EXTENDED）
5.  对频繁需要获取局部字符的大TEXT BYTEA ， 能提高读取效率

