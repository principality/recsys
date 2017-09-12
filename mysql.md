
# 关键特性

newsql introduce: https://zhuanlan.zhihu.com/p/26676711
alisql x-cluster: https://yq.aliyun.com/articles/165138

- 水平扩展，负载均衡，海量数据支持
- 秒级增加节点，分区自动调整
- 高可用性（金融级）: 异地多活
- AUTO FAILOVER
- OLTP + OLAP一体化

# 架构思考

```
+------------+
| mpp engine |------OLAP
+------------+
|mysql middle|------OLTP
+------------+
       |
+------------+
|  HA mysql  |
+------------+
```

- Mysql group replication for HA, R/W balance
- Add node to group for balance, Add group for scale
- add olap sql support to mpp engine
- reuse and exhance mysql middle ware

https://www.zhihu.com/question/53494990 分布式DB四问

# 资料

### mysql middle

- https://www.zhihu.com/question/31754653
- https://www.zhihu.com/question/37801919
- https://zhuanlan.zhihu.com/p/25864094
  - 读写分离 *
  - 垂直分库 *
  - 水平拆分
- proxysql/maxscale
- atlas
- mycat https://github.com/MyCATApache/Mycat-Server
  - 分布式算法实现不成熟，缺乏理论级和工业级支持
  - 缺少优化器，无法实现算法优化

### mysql cluster

- innodb cluster
- alisql x-cluster
- galera cluster
- percona cluster
- mariadb cluster

### distribute sql

- tidb
- tispark
