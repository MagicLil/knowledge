# Java 学习笔记

## 语言基础

- 面向对象三大特性：封装、继承、多态
- 值传递：Java 只有值传递，引用类型传递的是引用的副本
- 自动装箱/拆箱的坑：`Integer` 缓存范围为 -128 ~ 127，比较时注意使用 `equals`

## 集合框架

- `ArrayList`：数组实现，随机访问 O(1)，扩容 1.5 倍
- `LinkedList`：双向链表，增删快、查询慢
- `HashMap`：数组 + 链表 + 红黑树（JDK 8），链表长度 ≥ 8 且数组容量 ≥ 64 时树化
- `ConcurrentHashMap`：JDK 8 使用 CAS + synchronized 锁桶头节点

## 并发

- 线程状态：NEW → RUNNABLE → (BLOCKED / WAITING / TIMED_WAITING) → TERMINATED
- `synchronized`：锁对象头 Mark Word，JDK 6 后有偏向锁、轻量级锁升级机制
- `volatile`：保证可见性、禁止指令重排，不保证原子性
- 线程池核心参数：corePoolSize、maximumPoolSize、keepAliveTime、workQueue、RejectedExecutionHandler

## JVM

- 内存区域：堆、方法区（元空间）、虚拟机栈、本地方法栈、程序计数器
- GC 算法：标记-清除、标记-复制、标记-整理
- 常用收集器：G1（JDK 9+ 默认）、ZGC（低延迟）
- 类加载：双亲委派模型 —— 启动类加载器 → 扩展类加载器 → 应用类加载器

## 新特性（Java 17+）

- `record`：不可变数据载体，自动生成构造器、equals、hashCode、toString
- `sealed` 类：限制可继承的子类范围
- `switch` 表达式：支持箭头语法、可直接返回值
- 文本块：`"""..."""` 多行字符串
- Pattern Matching for `instanceof`：类型判断 + 强转一步完成

## 待深入

- [ ] JVM 调优实战
- [ ] JUC 源码（AQS）
- [ ] JVM 字节码与 invokedynamic

---

## 相关笔记

- [[Spring Boot 3]]
