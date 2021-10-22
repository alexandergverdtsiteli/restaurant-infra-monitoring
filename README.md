# restaurant-infra-monitoring
#bash
docker-compose up -d
#####################################################
GOTO for prometheus ===> http:localhost:9090
#####################################################
GOTO for grafana ===> http:localhost:3000
===> login ====> data source(config) ====>
Name:Prometheus
Type: Prometheus
URL: http://prometheus:9090
Access: proxy.
-------------------pretty fn(cpu_usage)-------------
===> login ====> data source(dashboard) ====> new ====> single stat
sum(rate(container_cpu_user_seconds_total{image!=""}[1m])) /
count(node_cpu{mode="system"}) * 100
#####################################################
