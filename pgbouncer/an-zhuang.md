# 安装

```
helm repo add icoretech https://icoretech.github.io/helm
helm repo update
// 安装
helm install pgbouncer icoretech/pgbouncer -f values.yaml -n cnpg-system --create-namespace
// 更新
helm upgrade pgbouncer icoretech/pgbouncer -f values.yaml -n cnpg-system
```
