# Alili Docker环境部署

## local
```shell
docker-compose up -d mysql redis etcd asynq-manage elasticsearch jaeger prometheus  grafana apisix-dashboard apisix apisix-nginx1 apisix-nginx2 golang
```

## test
```shell
docker-compose up -d portainer mysql redis asynq-manage elasticsearch jaeger prometheus etcd grafana apisix-dashboard apisix apisix-nginx1 apisix-nginx2
```
## pro
```shell
docker-compose up -d portainer  mysql-manage redis-manage asynq-manage elasticsearch jaeger prometheus
```

## aboard
```shell
docker-compose up -d portainer mysql-manage redis-manage asynq-manage elasticsearch jaeger prometheus etcd grafana apisix-dashboard apisix apisix-nginx1 apisix-nginx2
```