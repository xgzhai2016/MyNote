linkedBlockingQueue 要比arrayBlockingQueue可伸缩性好

AbstractQueuedSynchronizer\(AQS\),像Semaphroe，CountDownLatch，ReentrantLock，SynchronousQueue和FutrueTask都是基于AQS的。AQS解决了实现同步器涉及的大量细节。

AQS：

悲观锁：独占锁，只有其他线程不会造成干扰的情况下才会执行

乐观锁：通过冲突检查机制判断其他线程时候有干扰，若存在，则操作失败，然后重试（比较并交换CAS）





reentrantLock 并不是替换内置锁的方法，而是在内置锁不适用时，作为一种可选择的攻击功能。

synchronized局限：无法中断一个增在等待锁的线程，必须在获取该锁的代码块中释放锁等，lock可以避免死锁的发生

公平锁/非公平锁：公平锁中，线程按照请求顺序顺序回去锁，非公平锁中\(默认\)，则允许插队





内存栅栏：指令

指令重排：编译器生成的指令顺序与源代码不同，可以提高性能

