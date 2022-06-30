# 计算机系统漫游

1. 数字的机器表示与实际的整数 和实数是不同的，它们是对真值的有限近似值。

2. 编译系统由**预处理器(cpp)**、**编译器(ccl)**、**汇编器(as)**和**链接器(ld)**构成
3. 学习安全变成的第一步就是理解数据和控制信息存储在程序栈上的方式会引起的后果

4. 系统的硬件组成

- 总线
- I/O设备
- 主存
- CPU（寄存器，算术逻辑单元）

5. 程序运行的基本流程: I/O -> 硬盘 -> 主存 -> 寄存器 -> CPU -> 寄存器 -> I/O
6. 根据机械原理，较大的存储设备要比较小的存储设备运行的慢，而快速设备的造价远高于同类的低俗设备。

> 举例如下:
> 
> 硬盘容量为主存 1000 倍，但是对于处理器而言，从硬盘读取一个字的时间开销要比从主存中读取的开销大 1000 万倍。
> 
> 类似，寄存器只存储几百字节，主存可存放几十亿字节，处理器从寄存器中读取数据比从主存中读取几乎要快 100 倍。随着半导体技术的进步，处理器与主存间差距还在持续增大。因此，在处理器与主存间放置多级 **多级高速缓存存储器**

7. 操作系统有两个基本功能∶（1）防止硬件被失控的应用程序滥用；（2）向应用程序提供简单一致的机制来控制复杂而又通常大不相同的低级硬件设备。

8. 操作系统通过几个基本的抽象概念(**进程**、**虚拟内存**和**文件**)来实现这两个功能

- 文件是对 I/O 设备的抽象表示
- 虚拟内存是对主存和磁盘 I/O 设备的抽象表示
- 进程则是对处理器、主存和 I/O 设备的抽象表示

9. 从一个进程到另一个进程的转换是由操作系统**内核**（kernel）管理的。注意，内核不是一个独立的进程。相反，它是系统管理全部进程所用代码和数据结构的集合。
10. 虚拟内存是[操作系统](http://lib.csdn.net/base/operatingsystem)内核为了对进程地址空间进行管理（process address space management）而精心设计的一个逻辑意义上的内存空间概念。我们程序中的指针其实都是这个虚拟内存空间中的地址。进程占用虚拟内存空间大并非意味着程序的物理内存也一定占用很大。
11. **并发**（concurrency）是一个通用的概念，指一个同时具有多个活动的系统；而**并行**（parallelism）指的是用并发来使一个系统运行得更快。并行可以在计算机系统的多个抽象层次上运用。

- 线程级并发
- 指令级并行
- 单指令、多数据并行