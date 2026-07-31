# bot 与 echo连接的生命周期

一、没有长连接，只是一个请求

```
user -> "hello" -> telegram server -> https.post -> echo -> telebot handler
```
