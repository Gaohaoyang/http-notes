# 与 HTTP 关系密切的协议：IP、TCP和DNS

## 负责传输的 IP 协议

IP（Internet Protocol）网络协议位于网络层。

IP协议的作用是把各种数据包传送给对方。要确定传送到对方，需要满足各类条件。其中两个重要条件就是IP地址和MAC地址（Media Access Control Address）。

IP地址指明了节点被分配到的地址，MAC地址是指网卡所属的固定地址。

IP地址可以和MAC地址进行配对。IP地址可变换，但MAC地址基本上不会更改。

### 使用 ARP 协议凭借 MAC 地址进行通信

IP 间的通信依赖 MAC 地址。通信双方在同一局域网（LAN）内的情况是很多好的，通常是经过多台计算机和网络设备中转才能连接到对方。在进行中转时，会利用下一站中转设备的 MAC 地址来搜索下一个中转目标。这是会采用 ARP 协议（Address Resolution Protocol）。

ARP 是一种用以解析地址的协议，根据通信方的 IP 地址就可以凡查出对应的 MAC 地址。

### 没人能够全面掌握互联网中的传输状况

在到达通信目标前的中转过程中，那些计算机和路由器等网络设备只能熟悉很粗略的传输路线。

这种机制称为路由选择（routing）。

![](http://ww3.sinaimg.cn/large/7011d6cfjw1f01liwt6zkj20jm0hqac8.jpg)

## 确保可靠性的 TCP 协议

TCO 位于传输层，提供可靠的字节流服务。

字节流服务（Byte Stream Service），为了方便传输，将大块数据分割成以报文段（segment）为单位的数据包你进行管理。

### 确保数据能到达目标

为了准确无误的将数据送达目标处，TCP协议采用三次握手（three-way handshaking）策略。

![](http://ww3.sinaimg.cn/large/7011d6cfjw1f01lthkis7j20jp0aujsm.jpg)

若在握手过程中某个阶段莫名中断，TCP协议会再次以相同的顺序发送相同的数据包。
