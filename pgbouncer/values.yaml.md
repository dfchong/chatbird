# values.yaml

```
config:
  # 关键：使用通配符 *，而不是具体的 mydb
  databases:
    "*": "host=my-postgresql.default.svc.cluster.local port=5432"

  pgbouncer:
    pool_mode: transaction
    auth_type: scram-sha-256

  userlist:
    myuser: "my-password"

image:
  tag: "1.26.1"
```
