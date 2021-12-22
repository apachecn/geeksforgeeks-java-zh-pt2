# Java NIO 包中的 serverssocketchannel

> 原文:[https://www . geesforgeks . org/serverssocketchannel-in-Java-nio-package/](https://www.geeksforgeeks.org/serversocketchannel-in-java-nio-package/)

Java NIO **服务器套接字通道**是一个可以监听传入的 TCP 连接的通道，就像标准 Java 网络中的服务器套接字一样。ServerSocketChannel 类位于 java.nio.channels 包中。

```java
java.lang.Object
    java.nio.channels.spi.AbstractInterruptibleChannel
        java.nio.channels.SelectableChannel
            java.nio.channels.spi.AbstractSelectableChannel
                java.nio.channels.ServerSocketChannel
```

所有实现的接口:

```java
Closeable, AutoCloseable, Channel, InterruptibleChannel, NetworkChannel
```

```java
public abstract class ServerSocketChannel
extends AbstractSelectableChannel
implements NetworkChannel
```

**构造函数**

*   Protected Server Socket Channel (SelectorProvider provider): Initializes a new instance of this class.

#### 套接字通道的重要方法

*   **绑定(socket address local)**该方法用于将套接字通道绑定到本地地址，该地址作为参数提供给该方法。
*   **接受()**该方法用于接受与该通道插座的连接。
*   **连接(socket address remote)**此方法用于将套接字连接到远程地址。
*   **完成连接()**此方法用于完成插座通道的连接过程。
*   **getremote address()-**这个方法返回通道套接字连接的远程位置的地址。
*   **isConnected()-**如前所述，该方法返回插座通道的连接状态，即是否连接。
*   **Open()**Open 方法用于打开没有指定地址的套接字通道。这种方便的方法就像调用 open()方法一样，在生成的服务器套接字通道上调用 connect 方法，远程传递它，然后返回该通道。
*   **read(ByteBuffer dst)**此方法用于通过套接字通道从给定缓冲区读取数据。
*   **设置选项(插座选项< T >名称，T 值)**该方法设置插座选项的值。
*   **套接字()**该方法检索与该通道相关联的服务器套接字。
*   **有效操作()-**该方法返回一个操作集，标识该通道支持的操作。服务器套接字通道仅支持接受新连接，因此此方法返回 SelectionKey。OP_ACCEPT。

面向流的侦听套接字的可选通道。

服务器套接字通道是通过调用此类的 open 方法创建的。不可能为任意的、预先存在的服务器套接字创建通道。新创建的服务器套接字通道已打开，但尚未绑定。试图调用未绑定服务器套接字通道的接受方法将导致引发 NotYetBoundException。可以通过调用此类定义的绑定方法之一来绑定服务器套接字通道。

套接字选项是使用 setOption 方法配置的。服务器套接字通道支持以下选项:

```java
Option Name         Description
SO_RCVBUF             The size of the socket receive buffer
SO_REUSEADDR        Re-use address
```

还可能支持其他(特定于实现的)选项。

服务器套接字通道对于多个并发线程来说是安全的。

#### 这里有一个例子:

```java
ServerSocketChannel serverSocketChannel = ServerSocketChannel.open();

serverSocketChannel.socket().bind(new InetSocketAddress(9999));

while(true) {
   SocketChannel socketChannel = serverSocketChannel.accept();

   // Body
   // Do something with socketChannel...
}
```

**A.** 打开服务器套接字通道

您可以通过调用 ServerSocketChannel.open()方法来打开 ServerSocketChannel。

**语法:**

```java
ServerSocketChannel serverSocketChannel = ServerSocketChannel.open();
```

**B.** 关闭服务器插槽 1

关闭服务器套接字通道是通过调用服务器套接字通道. close()方法来完成的。

**语法:**

```java
serverSocketChannel.close();
```

**C.** 监听传入连接

侦听传入的连接是通过调用 ServerSocketChannel.accept()方法来完成的。当 accept()方法返回时，它返回一个带有传入连接的 SocketChannel。因此，accept()方法会一直阻塞，直到传入的连接到达。

因为您通常对只监听一个连接不感兴趣，所以您在 while 循环中调用 accept()。看起来是这样的:

**语法:**

```java
while(true) {
   SocketChannel socketChannel = serverSocketChannel.accept();
   // Do something with socketChannel...
}
```

当然，你会在 while 循环中使用一些其他的停止标准。

**D.** 非阻塞模式

服务器套接字通道可以设置为非阻塞模式。在非阻塞模式下，accept()方法会立即返回，因此如果没有传入连接到达，可能会返回 null。因此，您必须检查返回的 SocketChannel 是否为空。

**插图:**

```java
ServerSocketChannel serverSocketChannel = ServerSocketChannel.open();

serverSocketChannel.socket().bind(new InetSocketAddress(9999));
serverSocketChannel.configureBlocking(false);

while(true) 
{
   SocketChannel socketChannel = serverSocketChannel.accept();

   if(socketChannel != null)
   {
       // Do something with socketChannel...
   }
}
```