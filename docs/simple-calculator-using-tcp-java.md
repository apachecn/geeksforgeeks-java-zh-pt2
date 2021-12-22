# Java 中使用 TCP 的简单计算器

> 原文:[https://www . geesforgeks . org/simple-calculator-use-TCP-Java/](https://www.geeksforgeeks.org/simple-calculator-using-tcp-java/)

先决条件:[Java 中的 Socket 编程](https://www.geeksforgeeks.org/socket-programming-in-java/)
网络并不以客户机和服务器之间的单向通信结束。例如，考虑一个时间告知服务器，它监听客户端的请求，并以当前时间响应客户端。实时应用程序通常遵循通信的请求-响应模型。

客户端通常将请求对象发送到服务器，服务器在处理请求后，将响应发送回客户端。简而言之，客户端请求服务器上可用的特定资源，如果服务器能够验证该请求，它就会响应该资源。例如，当在输入期望的 url 后按下 enter 时，请求被发送到相应的服务器，然后服务器通过以浏览器能够显示的网页的形式发送响应来回复。
在本文中，实现了一个简单的计算器应用程序，其中客户端将以简单的算术等式的形式向服务器发送请求，服务器将以等式的答案作为响应。

**客户端编程**

客户端涉及的步骤如下-

1.  打开插座连接
2.  **Communication:** In the communication part, there is a slight change. The difference with the previous article lies in the usage of both the input and output streams to send equations and receive the results to and from the server respectively. [DataInputStream](https://www.geeksforgeeks.org/java-io-datainputstream-class-java-set-1/) and [DataOutputStream](https://www.geeksforgeeks.org/dataoutputstream-in-java/) are used instead of basic InputStream and OutputStream to make it machine independent. Following constructors are used –
    *   **公共数据输入流(input stream in)**t0]
    *   **公共数据输出流(InputStream in)**

        ```
        Syntax: public DataOutputStream(OutputStream out)
        Parameters:
        out - The underlying OutputStream.
        Creates a DataOutputStream that uses the specified underlying OutputStream.
        ```

    在创建输入和输出流之后，我们使用创建的流方法的 readUTF 和 writeUTF 分别接收和发送消息。

    *   **公共最终字符串 readUTF()
        抛出 IOException**T0】
    *   **公共最终字符串 writeUTF()
        抛出 IOException**

        ```
        Writes the string encoded using UTF8 encoding.
        Throws:
        IOException -  the stream has been closed and the contained input stream 
        does not support reading after close,
        or another I/O error occurs

        ```

3.  正在关闭连接。

**客户端实现**

```
// Java program to illustrate Client Side Programming
// for Simple Calculator using TCP
import java.io.DataInputStream;
import java.io.DataOutputStream;
import java.io.IOException;
import java.net.InetAddress;
import java.net.Socket;
import java.net.UnknownHostException;
import java.util.Scanner;

public class Calc_Client
{
    public static void main(String[] args) throws IOException
    {
        InetAddress ip = InetAddress.getLocalHost();
        int port = 4444;
        Scanner sc = new Scanner(System.in);

        // Step 1: Open the socket connection.
        Socket s = new Socket(ip, port);

        // Step 2: Communication-get the input and output stream
        DataInputStream dis = new DataInputStream(s.getInputStream());
        DataOutputStream dos = new DataOutputStream(s.getOutputStream());

        while (true)
        {
            // Enter the equation in the form-
            // "operand1 operation operand2"
            System.out.print("Enter the equation in the form: ");
            System.out.println("'operand operator operand'");

            String inp = sc.nextLine();

            if (inp.equals("bye"))
                break;

            // send the equation to server
            dos.writeUTF(inp);

            // wait till request is processed and sent back to client
            String ans = dis.readUTF();
            System.out.println("Answer=" + ans);
        }
    }
}
```

**输出**

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

**服务器端编程**

服务器端涉及的步骤如下-

1.  建立套接字连接。
2.  **处理来自客户端的等式:**在服务器端，我们也打开输入流和输出流。接收到这个等式后，我们对它进行处理，并通过在套接字的输出流上进行写操作将结果返回给客户端。
3.  关闭连接。

**服务器端实现**

```
// Java program to illustrate Server Side Programming
// for Simple Calculator using TCP
import java.io.DataInputStream;
import java.io.DataOutputStream;
import java.io.IOException;
import java.net.ServerSocket;
import java.net.Socket;
import java.util.StringTokenizer;

public class Calc_Server
{
    public static void main(String args[]) throws IOException
    {

        // Step 1: Establish the socket connection.
        ServerSocket ss = new ServerSocket(4444);
        Socket s = ss.accept();

        // Step 2: Processing the request.
        DataInputStream dis = new DataInputStream(s.getInputStream());
        DataOutputStream dos = new DataOutputStream(s.getOutputStream());

        while (true)
        {
            // wait for input
            String input = dis.readUTF();

            if(input.equals("bye"))
                break;

            System.out.println("Equation received:-" + input);
            int result;

            // Use StringTokenizer to break the equation into operand and
            // operation
            StringTokenizer st = new StringTokenizer(input);

            int oprnd1 = Integer.parseInt(st.nextToken());
            String operation = st.nextToken();
            int oprnd2 = Integer.parseInt(st.nextToken());

            // perform the required operation.
            if (operation.equals("+"))
            {
                result = oprnd1 + oprnd2;
            }

            else if (operation.equals("-"))
            {
                result = oprnd1 - oprnd2;
            }
            else if (operation.equals("*"))
            {
                result = oprnd1 * oprnd2;
            }
            else
            {
                result = oprnd1 / oprnd2;
            }
            System.out.println("Sending the result...");

            // send the result back to the client.
            dos.writeUTF(Integer.toString(result));
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

注意:为了在系统上测试上述程序，请确保您先运行服务器程序，然后运行客户端程序。确保您在客户端控制台中，并从那里输入格式为“操作 1 操作员操作 2”的等式，然后按回车键。对所请求等式的回答将仅在客户端控制台中显示。最后，要终止通信，请键入“bye”(不带引号)，然后按 enter 键。

**相关文章:**
[Java 中使用 UDP 的简单计算器](https://www.geeksforgeeks.org/simple-calculator-via-udp-in-java/)

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。