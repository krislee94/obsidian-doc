

###  虚拟化技术


如果要用简单的语句来阐述虚拟化技术的话，那么可以这么解释：

> 虚拟化技术是一种将计算机物理资源进行抽象、转换为虚拟的计算机资源提供给程序使用的技术。



### 容器技术


容器技术是一种全新意义上的虚拟化技术，按分类或者实现方式来说，其应该属于操作系统虚拟化的范畴，也就是在由操作系统提供虚拟化的支持。

能够让应用程序间可以互不干扰的独立运行，并且能够对其在运行中所使用的资源进行干预



### 虚拟机VS容器

![image](https://upload-images.jianshu.io/upload_images/5531021-68fc03148bd4ff46.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



由于没有了虚拟操作系统和虚拟机监视器这两个层次，大幅减少了应用程序运行带来的额外消耗。


更准确的来说，所有在容器中的应用程序其实完全运行在了宿主操作系统中，与其他真实运行在其中的应用程序在指令运行层面是完全没有任何区别的。


[[docker-思考题1]]



### Docker的技术实现


Docker 的实现，主要归结于三大技术：[[命名空间 ( Namespaces )]] 、[[控制组 ( Control Groups )]] 和 [[联合文件系统 ( Union File System )]] 。


但是这些技术是一些相对底层的原理实现，在Docker将它们封装后，我们并不会直接操作它们，在Docker中，另外提供出了一些软件层面的概念，这才是我们操作 Docker 所针对的对象。

在 Docker 体系里，有四个对象 ( Object ) 是我们不得不进行介绍的，因为几乎所有 Docker 以及周边生态的功能，都是围绕着它们所展开的。它们分别是：**镜像 ( Image )**、**容器 ( Container )**、**网络 ( Network )**、**数据卷 ( Volume )**。


[[镜像]] ，所谓镜像可以理解为一个只读的文件包，其中包含了**虚拟环境运行最原始文件系统的内容**。


[[容器]] ，就更好理解了，在容器技术中，容器就是用来隔离虚拟环境的基础设施。而在 Docker 里，它也被引申为隔离出来的虚拟环境。

[[网络]] ，对于大部分程序来说，它们的运行都不会是孤立的，而是要与外界或者更准确的说是与其他程序进行交互的，这里的交互绝大多数情况下指的就是数据信息的交换。网络通讯是目前最常用的一种程序间的数据交换方式了。

[[数据卷]]，能够简单的实现挂载，主要还是得益于 Docker 底层的 Union File System 技术。在 UnionFS 的加持下，除了能够从宿主操作系统中挂载目录外，还能够建立独立的目录持久存放数据，或者在容器间共享。


[[docker- 思考题3]]



### 搭建Docker运行环境

我使用的是mac系统。 mac系统本身就是基于linux系统的，因此，仅需在官网查看

[官网地址](https://docs.docker.com/get-docker/) 
![image.png](https://upload-images.jianshu.io/upload_images/5531021-392462c43bd34592.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


找到适合自己的版本。

我自己这是M1芯片的，根据官网的提示最好建议安装Rosetta 2. 

![image.png](https://upload-images.jianshu.io/upload_images/5531021-5b564e2e180b2c5e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


[官网安装目录](https://docs.docker.com/desktop/mac/install/)

启动一个docker

```
docker run -d -p 80:80 docker/getting-started

```

