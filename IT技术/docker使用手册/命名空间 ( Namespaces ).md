命名空间是 Linux 核心在 2.4 版本后逐渐引入的一项用于运行隔离的模块。

相信很多开发者在不同的编程语言中都见过命名空间的概念，在这些编程语言中，命名空间的主要目的就是为了集合相同模块的类，区分不同模块间的同名类。

同样的道理，Linux 内核的命名空间，就是能够将计算机资源进行切割划分，形成各自独立的空间。

就实现而言，Linux Namespaces 可以分为很多具体的子系统，如 User Namespace、Net Namespace、PID Namespace、Mount Namespace 等等。

这里我们以进程为例，通过 PID Namespace，我们可以造就一个独立的进程运行空间，在其中进程的编号又会从 1 开始。在这个空间中运行的进程，完全感知不到外界系统中的其他进程或是其他进程命名空间中运行的进程。


![image.png](https://upload-images.jianshu.io/upload_images/5531021-bd23b4371ceb6398.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


**利用 PID Namespace，Docker 就实现了容器中隔离程序运行中进程隔离这一目标。** 

