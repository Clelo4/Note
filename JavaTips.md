
## 1. Random vs ThreadLocalRandom

- Random is **thread safe** for use by **multiple threads**.
- **But if multiple threads use the same instance of Random**, the same **seed** is shared by multiple threads. It leads to contention between multiple threads and so to performance degradation. 
- ThreadLocalRandom is solution to above problem. ThreadLocalRandom has a Random instance per thread and safeguards against contention.
  
### 原因分析

- Random源码解析
    ```java
    protected int next(int bits) {
        long oldseed, nextseed;
        AtomicLong seed = this.seed;
        do {
            oldseed = seed.get();
            nextseed = (oldseed * multiplier + addend) & mask;
        } while (!seed.compareAndSet(oldseed, nextseed));
        return (int)(nextseed >>> (48 - bits));
    }
    ```
    每次调用next方法，尝试更新共享的seed，这会调用AtomicLong的compareAndSet方法，产生一定的性能影响，特别是在线程竞争激烈时，这个影响会扩大。


- ThreadLocalRandom避免线程竞争的原理

    每个线程都有自己的thread对象，ThreadLocalRandom将seed存储在各自的thread对象中，不会产生线程竞争。

## 2. Unsafe

From time to time, you may need to break the rules. In the Java platform, this is normally accomplished by using one of three primary mechanisms: reflection, class loading (including associated bytecode transformation), and Unsafe.

### 2.1 Unsafe allows developers to:
- Directly access CPU and other hardware features
- Create an object but not run its constructor
- Create a truly anonymous class without the usual verification
- Manually manage off-heap memory
- Do many other seemingly impossible things

## 3. Endianness

In Java, data is stored in **big-endian** format (also called network order).

## 4. 位操作

### 4.1 Java没有无符号位，所有算术类型都是有符号的

### 4.2 Java算术位移

| 类型 | 详情 | 符号 |
| --- | --- | --- |
| 算术左移 | 最后一位补0 | << |
| 算术右移 | 最前一位补0/1，如果是负数补1，正数补0  | >> |

### 4.3 Java逻辑位移

| 类型 | 详情 | 符号 |
| --- | --- | --- |
| 逻辑左移 | 最后一位补0 | 同算术左移 << |
| 逻辑右移 | 最前一位补0 | >>> |

### 4.4 特别注意byte类型的逻辑位移操作！！！

在逻辑位移操作中，byte类型会提升为int类型，导致出现意外结果

```java
byte a = (byte) 0xFA;
byte r1 = (byte) (a >>> 4); // r1的结果是0xFF
int i1 = a >>> 4; // i1的结果是0x00FFFFFF
```

在上面的逻辑右移操作中，类型为byte的a被提升成int类型，刚好a又是负数，a被提升为0xFFFFFFFA，
逻辑右移四位，最高位补0，得到0x00FFFFFF，转成byte类型，截取最低8位，得到0xFF，
所以在上面的例子中，r1的结果是0xFF，i1的结果是0x00FFFFFF

> 正确做法

```java
byte a = (byte) 0xFA;
byte r1 = (byte) ((a & 0xFF) >>> 4); // r1的结果是0x0F
int i1 = (a & 0xFF) >>> 4; // i1的结果是0x0F
```

# Java工具

https://docs.oracle.com/javase/8/docs/technotes/tools/unix/java.html