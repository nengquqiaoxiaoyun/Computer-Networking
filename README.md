## 计算机网络

- 反复记忆
- 多问为什么

### 大纲

计算机网络主要指的就是TCP/IP协议栈，是互联网的基石
容易忘是因为TCP/IP技术栈有一大部分都隐藏于操作系统的内核态，较少被接触。

#### 重点脉络

一、TCP/IP协议体系的认知
（1）分层。一部分处于用户态，一部分处于内核态。数据链路层，网络层，传输层封装于操作系统内核态。应用层存在于操作系统的用户空间，包括DNS，FTP，HTTPs，HTTP，工作中接触较多的是应用层的部分。但其它层的原理必须理解，面试考察。
（2）层与层之间下层对上层是透明的，传输在每一层是对等的。

二、数据链路层。
（1）以太网帧的格式。（2）MTU（最大传输单元）的概念。（3）ARP协议和RARP协议（地址协议和逆地址协议，网卡MAC地址和IP地址互查机制）（网络层和链路层的中间层）ARP报文格式，查询原理，缓存机制

三、网络层
（1）掌握IP首部格式：如16位分片标识、DF不分片标志、MF更多分片标志、13位片偏移、8位生存时间TTL、16位的首部检验和等等。
（2）掌握如何IP分片：如总长大于MTU值，画分片情况；如何避免IP分片（在应用层或传输层做限制）；确定分片顺序；确定分片是否全部到达。
（3）掌握IP选路。会看路由表。Route print 。路由表每个字段的含义
（4）掌握ICMP（因特网控制报文协议）：（理解为网络层和传输层的中间协议）报文格式；2种查询报文+5种差错报文。

四、传输层
（1）掌握UDP协议：无连接，不可靠的特点；首部各个字段
（2）掌握TCP协议（面试集中考察）：面向连接，可靠；首部各字段（序号，确认号，首部长度，窗口大小，校验和等特别的，完成可靠功能的部分）；TCP连接控制机制（三次握手，四次挥手，同时打开，同时关闭，半关闭）；TCP流量控制机制（滑动窗口、慢启动、拥塞避免、快速重传、快速恢复的算法原理）；TCP超时重传机制（四个定时器）；一些问题（为什么三次握手四次挥手？为什么TCP和UDP都存在尾包头？）
五、应用层
（1）掌握DNS（域名解析）协议：名字空间；DNS指针查询（反向查找或逆向解析）基本原理、DNS缓存
（2）FTP协议（活化石）：控制连接和数据连接（为什么需要这两种连接）；两种工作模式（PASV+PORT）；各种FTP指令和响应码；FTP断点续传，匿名FTP
（3）HTTP协议：报文格式（请求报文、响应报文、请求头各种字段、响应头各种字段）；HTTP状态码。
（4）HTTPS协议：详细握手过程；各种算法（摘要算法、数字签名、数字证书的原理与过程）