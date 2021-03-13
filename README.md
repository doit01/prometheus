prometheus moniter redis 
docker pull oliver006/redis_exporter
docker run -d --name redis_exporter -p 9121:9121 oliver006/redis_exporter --redis.addr redis://192.168.2.102:6379 --redis.password pwd
这里要写ip 。在我本机用docker的时候 如果用localhost不好使。

http://localhost:9121/metrics 会出现redis的metrics

如果garafana 不出来图，可能需要修改 该dashboard的variable ，改成constant 比较简单。
一个redis server 对应一个redis exporter

由于docker网络原因，最好，exporter和mysql 一个docker-compose。
prometheus和grafana一个docker-compose

