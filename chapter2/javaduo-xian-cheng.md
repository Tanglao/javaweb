* [volatile原理及应用](/chapter2/javaduo-xian-cheng.md#test)
* synchronized原理

* java内存模型

* ABA问题怎么解决的？

* 导致重排序的操作有哪些？

* happens-before、as if serial语义是什么意思
* 线程安全的单例
* 如何终止线程
* Daemon线程的作用？
* ConcurrentHashMap的实现?什么操作需要加锁？
* CopyOnWriteArrayList的原理
* ThreadLocal的实现
* CountDownLatch与CyclicBarrier的区别
* Semaphore信号量的作用
* Callable与Future
* 线程池有哪些？线程池的实现原理
* 无锁的实现方式
* Disruptor框架的实现原理
* 阻塞队列的实现原理
* 什么是AQS
* 公平锁的实现、读写锁的实现
* AIO与NIO的区别
* Actor并发模型的定义

##### volatile变量的写操作会使其他处理器的缓存行无效，其他处理器缓存行无效了就必须要从内存重新读。通常用于开关，单写多读。volatile保证了可见性、原子性



