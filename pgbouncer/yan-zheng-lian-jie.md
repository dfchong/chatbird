# 验证连接

```
kubectl run -it --rm test-pg --image=postgres:17 -- \
  psql -h my-pgbouncer -p 6432 -U myuser -d mydb -c "SELECT 1;"
```

