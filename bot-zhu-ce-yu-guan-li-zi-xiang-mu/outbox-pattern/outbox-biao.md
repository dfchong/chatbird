# outbox表

```
CREATE TABLE bot_event_outbox
(
    id BIGSERIAL PRIMARY KEY,

    aggregate_id BIGINT NOT NULL,
    event_type VARCHAR(64) NOT NULL,

    payload JSONB NOT NULL,

    published BOOLEAN DEFAULT false,

    retry_count INT DEFAULT 0,
    last_error TEXT,

    created_at TIMESTAMP DEFAULT NOW(),
    published_at TIMESTAMP
);

CREATE INDEX idx_outbox_unpublished 
ON bot_event_outbox(published, id);
```
