# 用 Java ping 一个 IP 地址|设置 1

> 原文:[https://www.geeksforgeeks.org/pinging-ip-address-java/](https://www.geeksforgeeks.org/pinging-ip-address-java/)

**PING** 在计算机网络领域代表 **Packet InterNet Groper** 。它是一种计算机网络管理软件，用于测试互联网协议网络上主机的可达性。它测量从始发主机发送到目标计算机并回显到源计算机的消息的往返时间。

Ping 通过向目标主机发送互联网控制消息协议(ICMP/ICMP6)回送请求数据包并等待 ICMP 回送回复来运行。该程序报告错误、数据包丢失和结果的统计摘要。

**互联网控制消息协议(ICMP) :** 互联网控制消息协议(ICMP)支持**互联网协议套件**中的协议。网络设备(如路由器)使用它来发送错误消息和操作信息，指示服务请求是否可用，或者无法联系到主机或路由器。
ICMP 与 TCP 和 UDP 等传输协议的不同之处在于，它通常不用于系统之间的数据交换。
在 Java 中不支持 ICMP，在 Java 中 ping 因为它依赖 ICMP
我们不能简单地在 Java 中 ping，因为它依赖 ICMP，遗憾的是在 Java 中不支持

这个 Java 程序使用[地址类](https://www.geeksforgeeks.org/networking-class-in-java/)在 Java 中 pings 一个 IP 地址。它在本地主机的情况下是成功的，但是对于其他主机，该程序显示主机不可访问。

```
// Java Program to Ping an IP address
import java.io.*;
import java.net.*;

class NewClass
{
  // Sends ping request to a provided IP address
  public static void sendPingRequest(String ipAddress)
              throws UnknownHostException, IOException
  {
    InetAddress geek = InetAddress.getByName(ipAddress);
    System.out.println("Sending Ping Request to " + ipAddress);
    if (geek.isReachable(5000))
      System.out.println("Host is reachable");
    else
      System.out.println("Sorry ! We can't reach to this host");
  }

  // Driver code
  public static void main(String[] args)
          throws UnknownHostException, IOException
  {
    String ipAddress = "127.0.0.1";
    sendPingRequest(ipAddress);

    ipAddress = "133.192.31.42";
    sendPingRequest(ipAddress);

    ipAddress = "145.154.42.58";
    sendPingRequest(ipAddress);
  }
}
```

**输出:**

```
Sending Ping Request to  127.0.0.1
Host is reachable
Sending Ping Request to  133.192.31.42
Sorry! We can't reach to this host
Sending Ping Request to  145.154.42.58
Sorry! We can't reach to this host

```

**下一步:** [用 Java ping 一个 IP 地址|集合 2(通过创建子进程)](https://www.geeksforgeeks.org/pinging-ip-address-java-set-2by-creating-sub-process/)

**定义来源:**
[https://en . Wikipedia . org/wiki/Internet _ Control _ Message _ Protocol](https://en.wikipedia.org/wiki/Internet_Control_Message_Protocol)
[https://en . Wikipedia . org/wiki/Ping _(networking _ utility)](https://en.wikipedia.org/wiki/Ping_(networking_utility))
本文由 <font color="green">**Mohit Gupta_OMG 供稿😀**</font> 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。