1. springcloud简介
2. 有哪些好的特性？
3. 各个组件的原理是什么？
4. 如何应对高并发、高可用？
5. 有哪些好的设计？

springcloud是一个分布式微服务框架

分布式服务组件有服务注册中心Eureka、服务配置中心、各种服务（服务提供、服务消费）。功能组件：网关zuul、负载均衡ribbon、熔断降级hystrix、生命式服务调用feign、消息中间件对接cloud stream、消息总线cloud bus、日志收集sleuth、服务监控

Eureka：高可用设计，设计为集群，结点之间相互注册，客户端定时发送心跳、定时更新本地服务信息、刷新服务状态。

优先调用同一个机房：一个region 有多个zone，优先找同一个zone的服务提供者，

ribbon：服务随机轮询、线性轮询、权重轮询（按响应时间）

feigin：封装客户端调用

zuul：实现本地跳转、请求过滤、重定向

hystrix：观察着模式、RxJava

