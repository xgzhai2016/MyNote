线程安全性：当多个线程访问一个类时，这个类的表现出的行为始终是正确的。

无状态对象一定是线程安全的，原子变量和同步一般不一块使用

---

重排：当没有同步时，编译器、处理器以及运行时都可能对程序执行顺序进行一定的调整

可见性：get/set方法都需要进行synchronized

volatile变量不会被缓存在寄存器，因此总是最新的。轻量级的同步机制，不会阻塞。不能保证原子性

---

线程封闭：将对象封装到线程中，这样就不用考虑对象是否是安全。JDBC

threadLocal：一般都是private static，ThreadLocal{ThreadLocalMap{entry},entry\[\]}，每个thread都维护了一个threadlocalmap映射表，key是threadLocal本身，value就是存储的object。entry是弱引用

![](/assets/threadLocal.PNG)

