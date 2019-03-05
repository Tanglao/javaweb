美团点评

1.MPP架构的系统（Presto/Impala/SparkSQL/Drill等）有很好的数

据量和灵活性支持，但是对响应时间是没有保证的。

2.搜索引擎架构的系统，在搜索类查询上能做到亚秒级响应。但

是对于扫描聚合为主的查询，随着处理数据量的增加，响应时间

也会退化到分钟级。

3.预计算系统（Druid/Kylin等）则在入库时对数据进行预聚合，进

一步牺牲灵活性换取性能，以实现对超大数据集的秒级响应

维度爆炸问题：Kylin可以把衍生维

度的计算从预计算推迟到查询处理阶段



美团外卖

在使用Kylin以

前，采用的是在Hive中开发聚合表再导入MySQL的方案。后面采用kylin，不需要数据仓库的汇总层



唯品会

自研自助分析平台-sqlparse-queryengin-redis-presto/kylin-hive/hadoop

es\druid join 不适合

在尝试Streaming Cubing、Lamda Cubing



百度外卖

OLAP引擎需求主要体现在支持的数据量、查

询性能、灵活性

Saiku+Mondrian对接Kylin

是Impala，优点是灵活，可以支持

各种类型的sql查询，但问题是用户的查询多了就会给Impala造成非常大

的压力，影响Impala每天例行的生产任务。且如果Sql比较复杂，Mpp架

构的查询引擎返回的时间会比较长甚至出错，数据查询效率较低



链家 GAIA



AWS 上 Apache Kylin 调度系统的设计

即使使用 Kylin 的 Kafka 构建模式仍然无 法实现亚分钟级别的实时数据查询。 为了解决这一问题，一种思 路是引进 Netflix Atlas、 Facebook Beringei 或 Yandex j 这样的时间序列数据库，用于取代 Kylin 满足对短时数据的实时 查询需求。



4399

用kylin解决口径不一致问题，不需要汇总层

