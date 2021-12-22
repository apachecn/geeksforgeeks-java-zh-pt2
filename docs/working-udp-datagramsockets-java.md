# 在 Java 中使用 UDP 数据图套接字

> 原文:[https://www . geeksforgeeks . org/working-UDP-datagramsockets-Java/](https://www.geeksforgeeks.org/working-udp-datagramsockets-java/)

数据图套接字是 Java 通过 UDP 而不是 TCP 进行网络通信的机制。Java 提供了 DatagramSocket 来通过 UDP 而不是 TCP 进行通信。它也建立在知识产权之上。数据图套接字可用于通过互联网发送和接收数据包。
UDP 优于 TCP 的一个例子是电视频道的直播。在这方面，我们希望向现场观众传输尽可能多的帧，而不用担心丢失一两帧。TCP 作为一种可靠的协议，在传输时会增加自身的开销。
另一个首选 UDP 的例子是在线多人游戏。在像反击或使命召唤这样的游戏中，没有必要传递所有的信息，只需要传递最重要的信息。还应该注意的是，现实生活中的大多数应用程序都小心翼翼地混合使用了 UDP 和 TCP 通过 TCP 传输关键数据，通过 UDP 传输其余数据。
本文是一个单边客户端-服务器程序的简单实现，其中客户端向服务器发送消息，服务器只打印消息，直到客户端发送“再见”。

**Java 数据报编程模型步骤**

*   **创建 DatagramSocket:-** 首先，创建一个 DatagramSocket 对象，将数据包携带到目的地，并在服务器发送任何数据时接收数据包。要创建 datagramSocket，可以使用以下构造函数:
    *   **受保护的 DatagramSocket DatagramSocket():**

```java
Syntax: public DatagramSocket()
              throws SocketException
Creates a datagramSocket and binds it to any available
port on local machine. If this constructor is used, the
OS would assign any port to this socket.
```

*   **受保护的 DatagramSocket DatagramSocket(int 端口):-**

```java
Syntax: public DatagramSocket(int port)
                        throws SocketException
Parameters:
port - port to which socket is to be bound
Throws:
SocketException - If the socket cannot be bound to the 
specific local port. Creates a DatagramSocket and binds 
to the specified port on the local machine.
```

*   **受保护的 DatagramSocket DatagramSocket(int port，InetAddress InetAddress):-**

```java
Syntax: public DatagramSocket(int port,
                       InetAddress inetaddress)
                        throws SocketException
Parameters:
port - port to which socket is to be bound.
inetaddress - local address to which socket is to be bound.
Throws:
SocketException - If the socket cannot be bound to the 
specific local port. It creates a DatagramSocket and 
binds it to specified port and ip-address.
```

*   **创建数据图包:**在此步骤中，创建用于通过数据图套接字发送/接收数据的包。
    *   发送数据的构造函数: **DatagramPacket(字节 buf[]，int 长度，InetAddress inetaddress，int 端口):-**

```java
Syntax: public DatagramPacket(byte[] buf,
              int offset,
              int length,
              SocketAddress address)
Parameters:
buf - the packet data.
offset - the packet data offset.
length - the packet data length.
address - the destination socket address.
Constructs a DatagramPacket for sending data at specified address
 and specified port.
```

构造函数来接收数据:

*   **数据分组(字节 buf[]，int 长度):-**

```java
Syntax: public DatagramPacket(byte buf[],
              int length)
Parameters:
buf - the packet data.
length - the packet data length.
Constructs a DatagramPacket for receiving the data of length length
in the byte array buf.
```

*   **调用套接字对象上的发送()或接收()调用**

```java
Syntax: void send(DatagramPacket packet)
                           throws SocketException
Parameters:
packet - Datagrampacket to send.
Throws:
SocketException - If there is an error in binding.
IllegalArgumentException - if address is not supported by the socket.
```

```java
Syntax: void receive(DatagramPacket packet)
                           throws SocketException
Parameters:
packet - Datagrampacket to receive from this socket.
Throws:
SocketException - If there is an error in binding.
IllegalArgumentException - if address is not supported by the socket.
```

**客户端实现**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate Client side
// Implementation using DatagramSocket
import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;
import java.util.Scanner;

public class udpBaseClient_2
{
    public static void main(String args[]) throws IOException
    {
        Scanner sc = new Scanner(System.in);

        // Step 1:Create the socket object for
        // carrying the data.
        DatagramSocket ds = new DatagramSocket();

        InetAddress ip = InetAddress.getLocalHost();
        byte buf[] = null;

        // loop while user not enters "bye"
        while (true)
        {
            String inp = sc.nextLine();

            // convert the String input into the byte array.
            buf = inp.getBytes();

            // Step 2 : Create the datagramPacket for sending
            // the data.
            DatagramPacket DpSend =
                  new DatagramPacket(buf, buf.length, ip, 1234);

            // Step 3 : invoke the send call to actually send
            // the data.
            ds.send(DpSend);

            // break the loop if user enters "bye"
            if (inp.equals("bye"))
                break;
        }
    }
}
```

**输出:**

```java
Hello
I am Client.
...
bye
```

**服务器端实现**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate Server side
// Implementation using DatagramSocket
import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;
import java.net.SocketException;

public class udpBaseServer_2
{
    public static void main(String[] args) throws IOException
    {
        // Step 1 : Create a socket to listen at port 1234
        DatagramSocket ds = new DatagramSocket(1234);
        byte[] receive = new byte[65535];

        DatagramPacket DpReceive = null;
        while (true)
        {

            // Step 2 : create a DatgramPacket to receive the data.
            DpReceive = new DatagramPacket(receive, receive.length);

            // Step 3 : revieve the data in byte buffer.
            ds.receive(DpReceive);

            System.out.println("Client:-" + data(receive));

            // Exit the server if the client sends "bye"
            if (data(receive).toString().equals("bye"))
            {
                System.out.println("Client sent bye.....EXITING");
                break;
            }

            // Clear the buffer after every message.
            receive = new byte[65535];
        }
    }

    // A utility method to convert the byte array
    // data into a string representation.
    public static StringBuilder data(byte[] a)
    {
        if (a == null)
            return null;
        StringBuilder ret = new StringBuilder();
        int i = 0;
        while (a[i] != 0)
        {
            ret.append((char) a[i]);
            i++;
        }
        return ret;
    }
}
```

简而言之，我们可以将通过 UDP 发送和接收数据的步骤总结如下

1.  对于通过 UDP 发送数据包，我们应该知道 4 件事，**要发送的消息，它的长度，目的地的 IP 地址，目的地监听的端口。**
2.  一旦我们知道了所有这些事情，我们就可以创建套接字对象来承载数据包和实际拥有数据的数据包。
3.  调用 send()/receive()调用实际发送/接收数据包。
4.  从接收到的数据包中提取数据。

**输出:**

```java
Client:- Hello
Client:- I am client.
...
Client:- bye
Client sent bye.....EXITING
```

注意:-为了在系统上测试上述程序，请确保您首先运行服务器程序，然后运行客户端程序。确保您在客户端控制台中，并从那里继续键入您的消息，每个消息后面都有一个回车。每次发送消息时，您将被重定向到服务器控制台，具体取决于您的环境设置。如果没有自动重定向，请切换到服务器控制台，以确保收到您的所有消息。最后，要终止通信，请键入“bye”(不带引号)，然后按 enter 键。
作为一个热情的读者，你也应该尝试并实现一个双向聊天应用程序，其中服务器将能够在他喜欢的时候回复消息。
**参考文献:**
[http://download . Java . net/JDK 7/archive/b123/docs/API/Java/net/datagramsocket . html](http://download.java.net/jdk7/archive/b123/docs/api/java/net/DatagramSocket.html)
T8】http://download . Java . net/JDK 7/archive/b123/docs/API/Java/net/datagramspacket . html
本文由 **Rishabh Mahrsee** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。