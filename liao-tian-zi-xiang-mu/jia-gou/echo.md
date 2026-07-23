# echo

* X-Telegram-Bot-Api-Secret-Token 提取
* auth
* rate limit
* traceid
* bot路由

```
e.POST("/webhook", func(c echo.Context) error {
    secret := c.Request().Header.Get("X-Telegram-Bot-Api-Secret-Token")
        //从请求头中提取secret-toke
    bot := botCache.Get(secret)
        // 区分bot
    var update telebot.Update
    if err := json.NewDecoder(c.Request().Body).Decode(&update); err != nil {
        return c.NoContent(400)
    }
        // 提取update
    // 组建 message
    // 发到 nats/jetstream
    return c.NoContent(200)
})
```

