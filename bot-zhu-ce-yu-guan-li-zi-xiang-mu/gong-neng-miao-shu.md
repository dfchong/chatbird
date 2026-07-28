# 功能描述

```
1. 这是一个telegram mini webapp
2. 此项目是多bot聊天平台的配套项目
3. 功能：
    - 提交bot_token注册，结果保存到redis/valkey和postgresql/jsonb
    - 修改注册信息
    - 删除注册信息
4. 注册/修改页面包含的字段有
    - bot_token（用户提交）
    - owner_id 自动提取
    - 是否参与自助推广（是/否）
    - 如参与自助推广，则欢迎词输入框为活动
    - 欢迎词出现在用户打开bot界面时
    - 欢迎词限300字
    - 如不参加自助推广，欢迎词后追加“绿能机器人承建”，点击进入绿能机器人频道
    - 如参加自助推广，欢迎词后追加“欢迎使用星际分类导航”，点进进入星际导航网站
5. 使用限制
    - 每个用户只能注册一个bot
    - 每个用户每天只能提交10次
    - 欢迎词只能使用文本，不支持多媒体
6. 技术栈
    - telegram mini webapp
    - tailwindcss
    - htmx
    - templ
    - echo
    - telebot
    - gorm
    - nats/jetstream
    - valkey
    - postgresql/json
7. 先讨论结构与实现方法，无需给出详细代码，如需要给出示例代码
```
