## Computer Networks
### Introduction
Personal Area Network | Local Area Network | Metro Area Network | Wide Area Network
网络的分类维度：传输技术|网络尺度
- 广播式链路和点到点链路
- PAN|LAN|MAN|WAN
计算机网络由资源子网、通信子网组成。软件、硬件以及数据属于资源子网，可以共享。
#### 协议栈
OSI参考模型：
- 传输层提供“端到端”的通信，其含义是源主机和目的主机的进程之间
TCP/IP参考模型：
- 在应用层、传输层、互联网层都定义了相应的协议和功能，但是网络接口层则沿用了OSI参考模型的相应标准，并没有定义其功能。
- 解决主机之间通信问题的是互联网层
> 通信子网，在OSI体系中的位置是下三层，分别是物理层、数据链路层、网络层。对应的TCP/IP参考模型内对应的层次有：互联网层、网络接口层
#### 服务和协议
*服务*是指某一层向它上一层提供的一组原语（操作）。服务定义了该层准备代表其用户执行哪些操作，但是它并不设计如何实现这些操作。*协议*是一组规则，规定了同一层上对等实体之间所交换的数据包或者报文的格式和含义。
网络协议包含以下要素：
- 语法，即数据与控制信息的结构或者格式
- 语义，即需要发出何种控制信息，完成何种动作以及作出何种响应
- 同步，即事件实现顺序的详细说明
#### 杂项
传输层是真正的端到端的层。
度量单位的混淆。
ARPAnet，分组交换
TCP/IP，无连接不可靠的数据包服务
网关，将两个或多个网络连接起来并提供必要转换的机器，其硬件和软件方面的总称
### 物理层
#### 通信基础
信道是指用来表示向某一个方向传播信息的介质。信号是指运载信息的工具，是信息的载体。
数据转换为模拟信号的过程称为调制，数据变换为数字信号的过程称为编码。PSK、QAM均为调制的方法，曼彻斯特编码是数字数据编码为数字信号的方法，PCM是将模拟信号编码为数字信号的方法。
信噪比通常表示为 $10\log_{10} \frac S N (dB)$ 
> 在使用时间域的波形表示数字信号时，代表不同离散数值的基本波形称为码元

**曼彻斯特编码**，又称为相位编码，是一种同步时钟编码技术，被物理层用于编码一个同步位流的事件和数据，被用在以太网媒介系统中。
- 在曼彻斯特编码中，每一位的中间有一跳变，位中间的跳变既作时间信号，又作数据信号；从低到高跳变表示“0”，从高到低跳变表示“1”
- 差分曼彻斯特编码，每位中间的跳变仅提供时钟定时，而用每位开始时有无跳变表示“0”或“1”，有跳变为“0”，无跳变为“1”
#### 交换方式
信元交换主要应用于ATM，是分组交换的一种。分组交换比报文交换的延时小，而电路交换采用独占链路，因此其延时最小。
### 应用层
Internet报文存取协议IMAP和POP3：
- 都是客户/服务器方式工作，POP3在脱机状态下运行，IMAP在联机状态下运行
- POP3时，邮件根据收件人的邮件地址交付给目的ISP邮件服务器，收件人不定期地连接到邮件服务器下载邮件，邮件的处理都是在用户地计算机上进行，因此POP3邮件服务器是一个具有存储转发功能的中间服务器。在邮件交付给用户之后，POP3服务器就不再保存这些邮件
- 同样是先送到ISP的邮件服务器的IMAP服务器，用户的计算机上运行IMAP客户程序，与ISP的邮件服务器上的IMAP服务器程序建立TCP连接。用户在自己的计算机上，就可以访问ISP的邮件服务器的邮箱，就像在本地使用一样。
> DHCP采用UDP来发送数据
