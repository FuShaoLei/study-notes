# 多线程

进程和线程：

- 进程：操作系统中独立运行的区域，进程和进程之间是独立的，数据是不共享的
- 线程：线程是运行在进程中的

简单的线程创建：

```java
// 方法1，重写Thread里的run方法
Thread thread = new Thread() {
    @Override
    public void run() {
        System.out.println("Thread started!");
    }
};
thread.start(); // 启动
// 方法2，新建一个Runnable类，然后传给Thread启动
Runnable runnable = new Runnable() {
    @Override
    public void run() {
        System.out.println("Thread with Runnable started!");
    }
};
Thread thread = new Thread(runnable);
thread.start();
```

线程池：

```java
Executor executor1 = Executors.newCachedThreadPool();// 常用的线程池
Executor executor2 = Executors.newSingleThreadExecutor();// 单线程的线程池
Executor executor3 = Executors.newFixedThreadPool(10);// 可以指定线程数量的线程池

// 甚至可以直接自定义
ExecutorService mExecutor = new ThreadPoolExecutor(5, 100, 5, TimeUnit.MINUTES, new SynchronousQueue<>());

```

Callable和Future：Callable相当于一个有返回值的Runnable，Future可以让你延迟获得

线程同步：

volatile关键字：积极的去维护同步，一般用多个线程去操作同一个变量的时候会用到

synchronized关键字：保证同步性

AtomicInteger等关键字：给变量加上原子性和同步性

