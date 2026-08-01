# webhook短缓存

```
1. echo收到bot_id
2. 查询bot:runtime:{bot_id}
3. 如果不存在，去pg查询
4. 写入vk
5. 模式：cache aside
```
