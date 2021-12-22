# 通过 Java 中的 UDP 实现的简单计算器

> 原文:[https://www . geesforgeks . org/simple-calculator-via-UDP-in-Java/](https://www.geeksforgeeks.org/simple-calculator-via-udp-in-java/)

网络是主机和服务器之间的双向通信，而不是信息交换。任何服务器都被设置为响应客户端请求的特定查询。根据向用户提供的实用程序，有许多不同类型的服务器。一些例子包括文件服务器、应用服务器、域服务器等。
让我们举一个例子来演示在客户机-服务器通信模型中，任何客户机的请求是如何处理的。假设 X 公司有数百名员工，每个人都在自己的系统上工作，大多数人使用打印机打印一些报告或发票等。在每个系统上安装打印机对于向用户提供打印设施的问题来说不是一个非常经济的解决方案。另一种方法是设置打印服务器，并在该系统上安装打印机。当员工想要打印东西时，他或她可以向服务器发送请求，要求为他/她保留打印机。接收请求的服务器让客户端程序根据许多因素(如打印机的可用性、传入请求的速率等)做出决定，最后响应请求，告知客户端打印机的状态。任何服务器的一个基本方面是它应该是特定的，而不是通用的。它不能对每个请求生成类似的响应，而是根据请求的性质、它所响应的客户端等进行响应。

本文通过 UDP 实现了一个简单的计算器-服务器，其中客户端将数学方程发送给服务器，服务器将给出方程的答案。

让我们首先讨论客户端编程，然后讨论服务器端编程。从客户端编程开始，如下所示:

**A.** 客户端编程

对于通过互联网发送或接收，需要知道监听实体的套接字地址，即监听程序的 IP 地址和端口号。通常，客户端知道，或者服务器转发它正在监听的套接字地址。所以在客户端，代码部分几乎没有变化。
客户端也调用 receive()调用，而不是只调用 send()调用。休息所有步骤保持不变。

涉及的步骤如下:

1.  **创建 DatagramSocket:** 首先，创建一个 DatagramSocket 对象，将数据包携带到目的地，并在服务器发送任何数据时接收数据包。
2.  **创建数据图包:**在此步骤中，创建用于通过数据图套接字发送/接收数据的包。
    注意:创建数据报包以发送和接收数据的构造函数是不同的
3.  **调用套接字对象上的 send()调用:**这将把我们携带等式的请求发送到服务器进行处理。
4.  **调用 socket 对象上的 receive()调用:**这是用来接收服务器处理完我们的请求后发送的数据。这将冻结我们的程序，直到服务器响应或抛出一个错误，如果它花了太多时间。

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate Client Side implementation
// of Simple Calculator using UDP

// Importing required classes
import java.io.IOException;
// Importing classes fromjava.nio package as
// this package is responsible for networking
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;
import java.util.Scanner;

// Main class
// Calc_Client_UDP
public class GFG {

    // Main driver method
    public static void main(String args[])
        throws IOException
    {

        // Creating an object of Scanner class to read user
        // input
        Scanner sc = new Scanner(System.in);

        // Step 1
        // Create the socket object for carrying data
        DatagramSocket ds = new DatagramSocket();

        InetAddress ip = InetAddress.getLocalHost();
        byte buf[] = null;

        // loop while user not enters "bye"
        while (true) {

            System.out.print(
                "Enter the equation in the format:");
            System.out.println(
                "'operand1 operator operand2'");

            // Awaiting from entered input
            String inp = sc.nextLine();
            buf = new byte[65535];

            // Converting the String input into the byte
            // array
            buf = inp.getBytes();

            // Step 2
            // Creating the datagramPacket for sending the
            // data.
            DatagramPacket DpSend = new DatagramPacket(
                buf, buf.length, ip, 1234);

            // Invoking the send call to actually send the
            // data.
            ds.send(DpSend);

            // Break the loop if user enters "bye"
            // using the break keyword
            if (inp.equals("bye"))
                break;

            buf = new byte[65535];

            // Creating an object of DatagramPacket class
            DatagramPacket DpReceive
                = new DatagramPacket(buf, buf.length);

            ds.receive(DpReceive);

            // Print and display command
            System.out.println(
                "Answer = "
                + new String(buf, 0, buf.length));
        }
    }
}
```

**输出:**

```
Enter the equation in the form: 'operand operator operand'
5 * 6
Answer=30
Enter the equation in the form: 'operand operator operand'
5 + 6
Answer=11
Enter the equation in the form: 'operand operator operand'
9 / 3
Answer=3
```

**B .服务器端编程**

由于通过互联网进行通信需要套接字地址，因此服务器必须知道客户端发送请求的地址。让我们一步一步来看服务器如何处理端口号的问题和响应客户端的查询。

客户端涉及的步骤如下:

1.  **建立插座连接**。
2.  **处理来自客户端的等式:**在服务器端，我们也打开输入流和输出流。收到等式后，我们对其进行处理并保存结果以发送回客户端。
3.  **创建数据包发送结果:**这一步会给服务器带来问题，因为它不知道客户端的端口号。为了获得端口，我们使用下面的 DatagramPacket 类的方法。
    T3】公众国际 getPort()

**语法:**

```
public int getPort()
Returns the port number to which the specified datagram packet is being sent to or
from which the packet is received.
```

> **注意:**最后一定要记得关闭连接，避免任何内存泄漏问题。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Illustrating Server Side Implementation
// of Simple Calculator using UDP

// Importing required classes
import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;
import java.util.StringTokenizer;

// Main class
// Calc_Server_UDP
class GFG {

    // MAin driver method
    public static void main(String[] args)
        throws IOException
    {

        // Creating a socket to listen at port 1234
        DatagramSocket ds = new DatagramSocket(1234);

        byte[] buf = null;

        // Initializing thm initially with null
        DatagramPacket DpReceive = null;
        DatagramPacket DpSend = null;

        while (true) {
            buf = new byte[65535];

            // Creating a DatagramPacket to receive the data.
            DpReceive = new DatagramPacket(buf, buf.length);

            // Receiving the data in byte buffer.
            ds.receive(DpReceive);

            String inp = new String(buf, 0, buf.length);

            // Using trim() method to
            // remove extra spaces.
            inp = inp.trim();

            System.out.println("Equation Received:- "
                               + inp);

            // Exit the server if the client sends "bye"
            if (inp.equals("bye")) {
                System.out.println(
                    "Client sent bye.....EXITING");

                // Exit from program here itself without
                // checking further
                break;
            }

            int result;

            // Use StringTokenizer to break the
            // equation into operand and operation
            StringTokenizer st = new StringTokenizer(inp);

            int oprnd1 = Integer.parseInt(st.nextToken());
            String operation = st.nextToken();
            int oprnd2 = Integer.parseInt(st.nextToken());

            // Perform the required operation
            if (operation.equals("+"))
                result = oprnd1 + oprnd2;

            else if (operation.equals("-"))
                result = oprnd1 - oprnd2;

            else if (operation.equals("*"))
                result = oprnd1 * oprnd2;

            else
                result = oprnd1 / oprnd2;

            System.out.println("Sending the result...");
            String res = Integer.toString(result);

            // Clearing the buffer after every message
            buf = res.getBytes();

            // Getting the port of client
            int port = DpReceive.getPort();

            DpSend = new DatagramPacket(
                buf, buf.length, InetAddress.getLocalHost(),
                port);
            ds.send(DpSend);
        }
    }
}
```

**输出:**

```
Equation received:-5 * 6
Sending the result...
Equation received:-5 + 6
Sending the result...
Equation received:-9 / 3
Sending the result...
```

> **注意:**为了在系统上测试上述程序，请确保您先运行服务器程序，然后运行客户端程序。确保您在客户端控制台中，并从那里输入格式为“操作 1 操作员操作 2”的等式，然后按回车键。对所请求等式的回答将仅在客户端控制台中显示。最后，要终止通信，请键入“bye”(不带引号)，然后按 enter 键。

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。