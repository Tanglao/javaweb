* [volatile原理及应用](/chapter2/javaduo-xian-cheng.md#volatile)
* [synchronized原理](/chapter2/javaduo-xian-cheng.md#synchronized)

* [java内存模型](/chapter2/javaduo-xian-cheng.md#jmm)

* [ABA问题怎么解决的？](/chapter2/javaduo-xian-cheng.md#aba)

* [导致重排序的操作有哪些？](/chapter2/javaduo-xian-cheng.md#chongpaixu)

* [happens-before、as if serial语义是什么意思](/chapter2/javaduo-xian-cheng.md#hb)

* [线程安全的单例](/chapter2/javaduo-xian-cheng.md#single)

* [如何终止线程](/chapter2/javaduo-xian-cheng.md#quit)

* [Daemon线程的作用？](/chapter2/javaduo-xian-cheng.md#Daemon)

* [ConcurrentHashMap的实现?什么操作需要加锁？](/chapter2/javaduo-xian-cheng.md#hashmap)

* [CopyOnWriteArrayList的原理](#copyonwritearraylist)

* [ThreadLocal的实现](/chapter2/javaduo-xian-cheng.md#threadlocal)

* [CountDownLatch与CyclicBarrier的区别](#countdownlatch与cyclicbarrier都是在一个或多个线程等待其他线程完成操作，join。cyclicbarrier循环栅栏可以多次使用)

* [Semaphore信号量的作用](/chapter2/javaduo-xian-cheng.md#semaphore)
* [Callable与Future](#callable)
* [线程池有哪些？线程池的实现原理](#threadpool)
* 无锁的实现方式
* Disruptor框架的实现原理
* 阻塞队列的实现原理
* 什么是AQS
* 公平锁的实现、读写锁的实现
* AIO与NIO的区别
* Actor并发模型的定义

##### volatile变量的写操作会使其他处理器的缓存行无效，其他处理器缓存行无效了就必须要从内存重新读。通常用于开关，单写多读。volatile保证了可见性、原子性 {#volatile}

##### synchronized 在代码块的前后分别加入monitorenter 、monitorexit指令 {#synchronized}

##### 线程之间的共享变量存储在主内存，每个线程有自己的本地内存，每个线程对于共享变量存储了副本 {#jmm}

##### aba问题时cas比较交换时原值跟期望值相同，但是原值中间发生了版本变化。通过对原值加个版本号，比较原值和版本号一致决定是否交换 {#aba}

##### 编译器优化、处理器指令并行执行、内存系统的重排序 {#chongpaixu}

##### hb 保证A操作可见于B，asifserial 不管怎么重排序，执行结果不会变 {#hb}

##### 懒汉式或者基于volatile的双重锁 {#single}

##### 通过状态控制让方法退出 {#quit}

##### Daemon守护线程是后台管理线程，用于支持其他线程工作，其他线程退出了，后台线程自动退出 {#daemon}

##### HashMap多线程会出现闭环问题，HashTable单锁会有性能问题。并发HashMap采用分段锁技术，segment和HashEntry即数组与链表，读取整个hashmap的size时会读取每个段的count （volatile类型的变量），如果modcout发生了变化，则需要加锁。 {#hashmap}

##### 每个ThreadLocal变量都有一个map，key就是当前线程，value就是值。get方法取值，set方法设置值 {#threadlocal}

##### CountDownLatch与CyclicBarrier都是在一个或多个线程等待其他线程完成操作，join。CyclicBarrier循环栅栏可以多次使用

##### Semaphore信号量控制线程数量为N，如控制一个线程池（线程数大于N）中连接数据库的线程数量 {#semaphore}

##### callable可以返回结果，Future不会返回结果 {#callable}

##### CopyOnWriteArrayList适用多读少写。写时会对list进行一个拷贝，拷贝前后的list里面的元素指向同一个引用。是一种读写分离的思想，保证最终一致性 {#copyonwritearraylist}

##### 线程池有可缓存的线程池cachedThreadPool，可以灵活回收与创建线程，FixedThreadPool 固定数量线程池，ScheduledThreadPool 周期性线程池，SingleThreadPool 单一线程池，保证只有一个线程执行，按先进先出处理任务。Executors工厂类创建线程池，Executor线程池接口。都是继承自ThreadPoolExecutor，里面维护了一个阻塞队列（有界队列、无界队列），可以采取拒绝策略：抛弃本身、抛弃旧任务，跑出异常，给当前线程跑。 {#threadpool}



