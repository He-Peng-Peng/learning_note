# docker

<img src="D:\HP_working_log\Learning\docker\img\720430-20181226134308841-1109691453.png" alt="720430-20181226134308841-1109691453" style="zoom:33%;" />




<img src="D:\HP_working_log\Learning\docker\img\720430-20181226134259735-1931086473.png" alt="720430-20181226134259735-1931086473" style="zoom:33%;" />


![720430-20181226134430830-648875754](D:\HP_working_log\Learning\docker\img\720430-20181226134430830-648875754.png)
Build, Ship and Run
搭建、发送、运行
Build once，Run anywhere（搭建一次，到处能用）

三大核心概念
* 镜像（Image）
* 容器（Container）
* 仓库（Repository）
官方的Docker Hub，这也是默认的Registry，并拥有大量的高质量的官方镜像


==K8S==，就是基于容器的集群管理平台，它的全称，是kubernetes。

<img src="D:\HP_working_log\Learning\docker\img\720430-20181226134529220-885595947.png" alt="720430-20181226134529220-885595947" style="zoom:50%;" />

Kubernetes这个单词来自于希腊语，含义是舵手或领航员。K8S是它的缩写，用“8”字替代了“ubernete”这8个字符。

和Docker不同，K8S的创造者，是众人皆知的行业巨头——**Google**

然而，K8S并不是一件全新的发明。它的前身，是Google自己捣鼓了十多年的**Borg系统**。

K8S是2014年6月由Google公司正式公布出来并宣布开源的。

一个K8S系统，通常称为一个**K8S集群（Cluster）**。

这个集群主要包括两个部分：

- **一个Master节点（主节点）**
- **一群Node节点（计算节点）**

![720430-20181226134539670-1577644922](D:\HP_working_log\Learning\docker\img\720430-20181226134539670-1577644922.png)

Master节点主要还是负责管理和控制。Node节点是工作负载节点，里面是具体的容器

首先来看master节点： 

![720430-20181226134549651-376208258](D:\HP_working_log\Learning\docker\img\720430-20181226134549651-376208258.png)

其中包括：    API Server、Scheduler、Controller manager、etcd

1. API Server是整个系统的对外接口，供客户端和其它组件调用，相当于“营业厅”。

2. Scheduler负责对集群内部的资源进行调度，相当于“调度室”。

3. Controller manager负责管理控制器，相当于“大总管”。

然后是node节点：

![720430-20181226134600202-626807958](D:\HP_working_log\Learning\docker\img\720430-20181226134600202-626807958.png)

Node节点包括Docker、kubelet、kube-proxy、Fluentd、kube-dns（可选），还有就是**Pod**。

> Pod是Kubernetes最基本的操作单元。一个Pod代表着集群中运行的一个进程，它内部封装了一个或多个紧密相关的容器。除了Pod之外，K8S还有一个Service的概念，一个Service可以看作一组提供相同服务的Pod的对外访问接口。这段不太好理解，跳过吧。

**docker** 创建容器，**Kubelet** 监视指派到它所在Node上的Pod，包括创建，修改，监控，删除等。

**Kube-proxy**，主要负责为Pod对象提供代理。

**Fluentd**，主要负责日志收集、存储与查询。

