## 高性能分布式日志系统

1.apache bookkeeper / DistributeLog 分布式日志需要重点解决哪些问题？2.还有哪些日志系统3.对比公司的DS，有哪些优缺点4.团队是否可以采用

## 腾讯防刷架构

1.架构怎么设计2.其他厂商如何设计3.对比公司，有哪些不同4.团队是否可以采用

## 高可用架构原理与分布式实践redis

1.redis 高可用方案如何做 。

* 哨兵机制\(Sentinel\) 主从切换主从同步复制，降低性能。异步复制，会存在丢失

* proxy HA

  * Keepalived（Heartbeat、Corosync）前端负载均衡高可用

  * HAProxy 负载均衡 tcp四层 tcp七层 的软件

2.spanner是啥？3.go的gc有什么问题，对比jvm gc有什么优缺点4.redis集群方案

* Twemproxy 扩容缩容麻烦

* codis（豌豆荚开发）性能好，有server-group（master/slave）概念。

* redis-cluster，无中心节点5.redis与memcache对比6.redis单线程问题7.物理redis分片算法

## Lambda架构与推荐在电商网实战

1.Lambda是什么架构2.storm、spark、samza对比

* 状态管理

* 消息传输可靠保障

* 容错机制

* 吞吐量、性能

* 时延

* 编程模型3.对比当前项目的使用4.团队是否可以采用

## 线上真实流量压测

1.压测有哪些问题要处理2.压测工具有哪些3.压测系统设计3.InfluxDB 是什么

## 大数据架构

1.实时分层2.kafka-hdfs3.storm本地存储

## 360-bada

1.适合哪些应用场景2.主从模式跟无主从结构对比3.Cassandra、MongoDB的设计是怎么样4.LevelDB是what5.kafka如何保证消息的可靠性6.Vector Lock 是什么7.多机房写入冲突的解决方案8.Mnesia跟Zk对比9.RocksDB对比LevelDB10.扩容是主机数据不可用的问题

## Elastic-Job

1.什么场景需要分布式调度、任务分片2.Elastic-Job源码阅读。任务挂了怎么办？怎么部署3.Lombok what？

## 20180118 交易中心稳定优化

1.Nginx限流、tomcat限流对比2.事务消息3.分布式事务、分库分表（按买家、卖家）一致性4.suirvivor调小的问题

