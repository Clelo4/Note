- [1. 多线程技术简介](#1-多线程技术简介)
  - [1.1 为什么需要并发](#11-为什么需要并发)
  - [1.2 进程和线程的区别](#12-进程和线程的区别)
  - [1.3 线程操作：启动、Interrupts和join](#13-线程操作启动interrupts和join)
    - [1.3.1 启动](#131-启动)
    - [1.3.2 Interrupts](#132-interrupts)
    - [1.3.3 Joins](#133-joins)
- [2. 多线程的两个重点问题](#2-多线程的两个重点问题)
  - [2.1 为什么会出现Memory Consistency Errors（内存一致性错误）？](#21-为什么会出现memory-consistency-errors内存一致性错误)
  - [2.2 如何解决内存一致性错误？](#22-如何解决内存一致性错误)
  - [2.3 如何建立happen-before关系](#23-如何建立happen-before关系)
- [3. synchronized](#3-synchronized)
  - [3.1 synchronized方法](#31-synchronized方法)
  - [3.2 synchronized表达式](#32-synchronized表达式)
  - [Reentrant Synchronization（可重入锁）](#reentrant-synchronization可重入锁)
  - [3.3 Atomic Action（原子操作）](#33-atomic-action原子操作)
  - [3.4 Using volatile variables reduces the risk of memory consistency errors](#34-using-volatile-variables-reduces-the-risk-of-memory-consistency-errors)
- [4. 锁的存活性](#4-锁的存活性)
- [5. Java.util.concurrent](#5-javautilconcurrent)
  - [5.1 Atomic Variables](#51-atomic-variables)
  - [5.2 Lock Objects](#52-lock-objects)
  - [5.3 Executor](#53-executor)
  - [5.4 Concurrent Collections](#54-concurrent-collections)
  - [5.5 Concurrent Random Number](#55-concurrent-random-number)
- [6. 并发编程的三个关键问题](#6-并发编程的三个关键问题)
  - [6.1 原子性问题](#61-原子性问题)
  - [6.2 可见行问题](#62-可见行问题)
  - [6.3 有序性问题](#63-有序性问题)
- [7. Java内存模型（Java Memory Model，JMM）](#7-java内存模型java-memory-modeljmm)
- [8. volatile关键字](#8-volatile关键字)
- [9. 多线程的常见问题](#9-多线程的常见问题)
  - [9.1 实现多线程单例模式的五种常见方式](#91-实现多线程单例模式的五种常见方式)
    - [9.1.1 double-check技术](#911-double-check技术)
        - [为什么double-check技术必须使用volatile？](#为什么double-check技术必须使用volatile)
- [10. CAS操作](#10-cas操作)
  - [10.1 原理](#101-原理)
  - [10.2 ABA问题](#102-aba问题)
  - [10.3 CAS循环时间长开销大](#103-cas循环时间长开销大)
  - [只能保证一个共享变量的原子操作](#只能保证一个共享变量的原子操作)
- [11. 原子操作实现方法](#11-原子操作实现方法)
  - [11.1 CAS操作](#111-cas操作)
  - [11.2 使用锁机制实现原子操作](#112-使用锁机制实现原子操作)
- [12. 锁机制](#12-锁机制)


# 1. 多线程技术简介

## 1.1 为什么需要并发

- 在某些CPU中，只有一个执行核心。任何时刻，一个执行核心只能有一个进程在执行，但通过系统特性，多个进程可以通过分时技术共享CPU资源，由于CPU执行速度很快，这种分时技术可以提升CPU执行效率。
- 现代CPU有多个处理器（如双路CPU）或者多个执行核心（多核技术），允许通过多个进程和线程同时运行。但即使只有一个处理器和一个执行核心，也可以进行并发（利用上面提到的分时技）。
- CPU执行速度很快，高于文件操作和内存操作等，为了不降低CPU执行效率，可以在操作文件或内存时，释放CPU资源，等文件或内存操作完时，在重新获取CPU资源继续执行

## 1.2 进程和线程的区别

- 进程是程序的一次执行过程，是资源分配的基本单位，具有独立的内存空间和系统资源 
-  线程是进程中的一个执行单元，是CPU调度的基本单位，共享进程的内存空间和系统资源

| 特性	| 进程 | 线程 |
| ---- | ---- | ------|
| 资源占用 | 每个进程都有自己的地址空间和系统资源，占用更多的内存和 CPU 资源  | 所有线程共享进程的地址空间和系统资源，占用较少的内存和 CPU 资源 |
| 通信方式 | 进程间通信需要使用 IPC（Inter-Process Communication）机制，如管道、消息队列、共享内存等  | 线程间通信可以直接访问共享变量或使用线程间通信机制，如 wait()、notify()、notifyAll  () 等 |
| 数据共享  | 	进程间数据共享需要使用 IPC 机制，如共享内存、文件等  | 	线程间数据共享可以直接访问共享变量 |
| 同步机制  | 	进程间同步需要使用 IPC 机制，如信号量、互斥锁、条件变量等  | 线程间同步可以使用 synchronized 关键字、Lock 接口、volatile 关键字等 |
| 创建和销毁 | 	创建和销毁进程需要较多的系统资源和时间 | 	创建和销毁线程比较快，开销较小 |
| 安全性 | 进程间相互独立，一个进程崩溃不会影响其他进程 | 	线程间共享地址空间和资源，一个线程崩溃可能会导致整个进程崩溃 |
| 可扩展性 | 	进程间可扩展性较好，可以在不同的机器上运行 | 	线程间可扩展性较差，受限于 CPU 和内存等资源的限制 |


## 1.3 线程操作：启动、Interrupts和join

### 1.3.1 启动

- Implements Runnable
```java
public class HelloRunnable implements Runnable {

    public void run() {
        System.out.println("Hello from a thread!");
    }

    public static void main(String args[]) {
        (new Thread(new HelloRunnable())).start();
    }

}
```

- Extends Thread
```java
public class HelloThread extends Thread {

    public void run() {
        System.out.println("Hello from a thread!");
    }

    public static void main(String args[]) {
        (new HelloThread()).start();
    }

}
```

### 1.3.2 Interrupts

- An interrupt is an indication to a thread that it should stop what it is doing and do something else.
- It's up to the programmer to decide exactly how a thread responds to an interrupt.
- but it is very common for the thread to terminate. This is the usage emphasized in this lesson.

| 操作类型 | 解释 |
| ------ | ------|
| isInterrupted() 方法 | Thread 类的实例方法，用于检查当前线程是否被中断。它不会清除中断状态，即使线程被中断了，调用 isInterrupted() 方法也会返回 true |
| Thread.interrupted() 方法 | interrupted() 方法是 Thread 类的静态方法，用于检查当前线程是否被中断，并清除中断状态。如果线程被中断了，调用 interrupted() 方法会返回 true，并清除中断状态；如果线程没有被中断，调用 interrupted() 方法会返回 false |
| 线程的 interrupt() 方法 | 触发线程中断 |

### 1.3.3 Joins

等待某个线程结束

# 2. 多线程的两个重点问题

- thread interference（线程干涉）
- memory consistency errors（内存一致性错误）

## 2.1 为什么会出现Memory Consistency Errors（内存一致性错误）？

- 内存一致性错误：不同线程访问同一个数据，但拿到不同的内容。
- CPU每个核心都有独立的缓存，导致不同线程的缓存数据可能不一致的，这就是所谓的内存一致性错误。

## 2.2 如何解决内存一致性错误？

> 途径：建立happens-before关系

> 什么是happen-before关系？

The results of a write by one thread are guaranteed to be visible to a read by another thread only if the write operation happens-before the read operation. 

## 2.3 如何建立happen-before关系

- Each action in a thread happens-before every action in that thread that comes later in the program's order.
- An **unlock** (synchronized block or method exit) of a **monitor** happens-before every subsequent **lock** (synchronized block or method entry) of that **same monitor**. And because the happens-before relation is transitive, all actions of a thread prior to unlocking happen-before all actions subsequent to any thread locking that monitor.
- A write to a **volatile** field happens-before every subsequent read of that same field. Writes and reads of volatile fields have similar memory consistency effects as entering and exiting monitors, but do not entail mutual exclusion locking.
- A call to **start** on a thread happens-before any action in the started thread.
- All actions in a thread happen-before any other thread successfully returns from a **join** on that thread.

# 3. synchronized

## 3.1 synchronized方法

| 类型 | 锁定对象 | 限制 |
| ---- | ---- | ---- |
| synchronized静态方法 | 当前类的monitor lock | 不能同时运行多个synchronized静态方法 |
| synchronized实例方法 | 当前实例的monitor lock | 不能同时运行多个synchronized实例方法 |

> 注意：
> 由于synchronized静态方法和synchronized实例方法分别使用不同的monitor lock，所以两者互不影响。
> 如果synchronized静态方法和synchronized实例方法分别访问同一个static field，可产生错误。

## 3.2 synchronized表达式

与synchronized方法区别，synchronized表达式可以自定义锁对象，作为一个整体block。

## Reentrant Synchronization（可重入锁）

A thread can acquire a lock that it already owns.

## 3.3 Atomic Action（原子操作）

- Reads and writes are atomic for reference variables and for **most primitive variables** (all types except **long** and **double**).
- Reads and writes are atomic for all variables declared **volatile** (including **long** and **double** variables).

> ⚠️注意：Atomic Action can't eliminate memory consistency errors problems.

原子操作如何保证内存一致性呢？
- 1. 使用synchronization
- 2. 使用JUC的atomic methods

## 3.4 Using volatile variables reduces the risk of memory consistency errors

because any write to a volatile variable establishes a **happens-before** relationship with subsequent reads of that same variable.

# 4. 锁的存活性

| 类型 | 说明 |
| ------ | ------- |
| 死锁（deadlock） | Deadlock describes a situation where two or more threads are blocked forever, waiting for each other. |
| 活锁（livelock） | A thread often acts in response to the action of another thread. If the other thread's action is also a response to the action of another thread, then livelock may result. As with deadlock, livelocked threads are unable to make further progress. However, the threads are not blocked — they are simply too busy responding to each other to resume work. This is comparable to two people attempting to pass each other in a corridor: Alphonse moves to his left to let Gaston pass, while Gaston moves to his right to let Alphonse pass. Seeing that they are still blocking each other, Alphone moves to his right, while Gaston moves to his left. They're still blocking each other, so... |
| 饥饿锁（starvation lock） | Starvation describes a situation where a thread is unable to gain regular access to shared resources and is unable to make progress. This happens when shared resources are made unavailable for long periods by "greedy" threads. For example, suppose an object provides a synchronized method that often takes a long time to return. If one thread invokes this method frequently, other threads that also need frequent synchronized access to the same object will often be blocked. |

# 5. Java.util.concurrent

## 5.1 Atomic Variables

- 上文提到，原子操作（Atomic action）不能解决内存一致性错误
- JUC的原子变量，写操作会与后续的读操作建立happen-before关系。

## 5.2 Lock Objects


## 5.3 Executor

## 5.4 Concurrent Collections

## 5.5 Concurrent Random Number

# 6. 并发编程的三个关键问题

## 6.1 原子性问题

## 6.2 可见行问题

## 6.3 有序性问题

- 重排序问题：程序在运行时，可能不会按照程序代码的出现顺序执行，而是经过了重排序。
```java
// 代码的顺序
int i = 0;
boolean flag = true;

// 实际的执行顺序可能是这样的
boolean flag = true;
int i = 0;
```
- 重排序种类：
  - 编译器级重排序：编译器的优化策略可能会改变代码的实际执行顺序。
  - 指令性级重排序：在CPU乱序执行的情况下，CPU可以根据指令之间的依赖关系和可执行性进行动态调度，从而避免了指令之间的等待和浪费，提高了CPU的执行效率和性能。

- 重排序的目的：
    重排序的目的是为了提高程序的执行效率和性能


# 7. Java内存模型（Java Memory Model，JMM）

# 8. volatile关键字

- 解决缓存可见性问题
- 避免重排序

# 9. 多线程的常见问题

## 9.1 实现多线程单例模式的五种常见方式

### 9.1.1 double-check技术

```java
class Singleton{
    private volatile static Singleton instance = null;
     
    private Singleton() {
         
    }
     
    public static Singleton getInstance() {
        if(instance==null) {
            synchronized (Singleton.class) {
                if(instance==null)
                    instance = new Singleton();
            }
        }
        return instance;
    }
}
```

##### 为什么double-check技术必须使用volatile？

# 10. CAS操作

## 10.1 原理

使用CMPXCHG指令，自旋CAS实现的基本思路就是循环进行CAS操作直到成功为止

```java
public void safeCount() {
  while (true) {
    int i = atomicT.get();
    boolean suc = atomicT.compareAndSet(i, ++i);
    if (suc) break;
  }
}
```

## 10.2 ABA问题

因为CAS需要在操作值的时候，检查值有没有发生变化，如果没有发生变化 则更新，但是如果一个值原来是A，变成了B，又变成了A，那么使用CAS进行检查时会发现它 的值没有发生变化，但是实际上却变化了。

解决方法：
ABA问题的解决思路就是使用版本号。在变量前面 追加上版本号，每次变量更新的时候把版本号加1，那么A→B→A就会变成1A→2B→3A。

## 10.3 CAS循环时间长开销大

自旋CAS如果长时间不成功，会给CPU带来非常大的执行开销

## 只能保证一个共享变量的原子操作

AtomicReference??

# 11. 原子操作实现方法

## 11.1 CAS操作

## 11.2 使用锁机制实现原子操作

# 12. 锁机制

有偏向锁、轻量级锁和互斥锁