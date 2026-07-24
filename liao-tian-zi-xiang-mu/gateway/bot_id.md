# bot\_id

一、

1. 从头中提取secret\_token
2. 根据secret\_toke去redis提取bot\_id

```
secret := c.Request().Header.Get("X-Telegram-Bot-Api-Secret-Token")
if secret == "" {
    return c.NonContent(403)
}

// redis
key := "telegram:webhook:secret:" + secret
data, err := redis.Get(c.Request().Context(), key).Bytes()
if err != nil {
    return c.NonContent(403)
}

// 
var bot BotInfo
json.Unmarshal(data, &bot)

//
var update telebot.Update
if err := c.Bind(&update); err != nil {
    return c.NoContent(400)
}

// msg-id
```
