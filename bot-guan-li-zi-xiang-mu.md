# bot管理子项目

项目一、bot管理 chatbird聊天平台子项目，管理bot的工具 聊天平台 前端：

1. 添加bot 用户群 用户频道 用户广告语
2. 删除bot
3. 修改bot 后端：
4. 添加bot 生成scret\_toke 将bot-id与生成的secret\_token添加到kvrocks的hash表中 广告信息添加到PG
5. 删除bot 从hash表中删除bot-id 与 对应的 secret\_token 按照bot-id，从PG中删除广告信息
