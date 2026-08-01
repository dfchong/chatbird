# 用户bot注册表

1. 表名：bot\_registry
2. sehema

```
CREATE TABLE bot_registry (
    id BIGSERIAL PRIMARY KEY,
    
    -- Telegram Mini App 用户
    owner_id BIGINT NOT NULL,
    
    -- Telegram Bot 信息
    bot_id BIGINT NOT NULL,
    bot_username VARCHAR(255),
    
    -- token加密保存
    bot_token_ciphertext TEXT NOT NULL,
    
    -- 状态
    status VARCHAR(32) NOT NULL DEFAULT 'active',    
    /*
       active
       disabled
       deleted
    */
    
    -- 是否参与推广
    promotion_enabled BOOLEAN NOT NULL DEFAULT false,
    
    -- 欢迎词
    welcome_text VARCHAR(300),
    
    -- 扩展配置
    config JSONB NOT NULL DEFAULT '{}',
    
    -- 创建时间
    created_at TIMESTAMP NOT NULL DEFAULT NOW(),
    updated_at TIMESTAMP NOT NULL DEFAULT NOW(),
    
    -- 一个用户只能一个bot，防止
    CONSTRAINT uq_bot_owner 
        UNIQUE(owner_id),
        /* 
    -- 一个telegram bot只能注册一次,防止多个用户注册同一个bot
    CONSTRAINT uq_telegram_bot
        UNIQUE(bot_id)
);
```
