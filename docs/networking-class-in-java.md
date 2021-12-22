# Java 中的联网|集 1 (Java.net.InetAddress 类)

> 原文:[https://www.geeksforgeeks.org/networking-class-in-java/](https://www.geeksforgeeks.org/networking-class-in-java/)

这个类代表一个 IP 地址。它代表 32 位 IPv4 地址和 128 位 IPv6 地址。它是 Inet6Address 和 Inet4Address 类的超类。该类的一个实例由一个 IP 地址和一个主机名组成，这取决于主机名解析是否在创建过程中执行。
推荐阅读: [IP 寻址|简介](https://www.geeksforgeeks.org/ip-addressing-introduction-and-classful-addressing/)
这个类没有构造函数，只有静态方法，返回 InetAddress 类的实例供一般使用。

**方法:**

1.  **getAddress() :** 将此 InetAddress 对象的原始 IP 地址作为数组返回。字节在数组中出现的顺序与在 IP 地址中的顺序相同，即 getAddress[0]将包含最高顺序的字节。

    ```
    Syntax : public byte[] getAddress()
    ```

2.  **getHostAddress() :** 以文本形式返回 IP 地址。

    ```
    Syntax :public String getHostAddress()
    ```

3.  **is anilocaladdress():**如果该地址代表本地地址，则返回 true。

    ```
    Syntax :public boolean isAnyLocalAddress()
    ```

4.  **islinklocaldaddress():**如果该地址是链路本地地址，则返回 true。

    ```
    Syntax :public boolean isLinkLocalAddress()
    ```

5.  **isLoopbackAddress() :** 如果该地址是环回地址，则返回 true。

    ```
    Syntax :public boolean isLoopbackAddress()
    ```

6.  **isMCGlobal() :** 如果此多播地址具有全局作用域，则返回 true。

    ```
    Syntax :public boolean isMCGloabal()
    ```

7.  **IsmCellLocal():**如果此多播地址有链接范围，则返回 true。

    ```
    Syntax :public boolean isMCLinkLocal()
    ```

8.  **如果此多播地址具有节点作用域，则 isMCNodeLocal() :** 返回 true。

    ```
    Syntax :public boolean isMCNodeLocal()
    ```

9.  **如果此多播地址具有组织范围，则 isMCOrgLocal() :** 返回 true。

    ```
    Syntax :public boolean isMCOrgLoacal()
    ```

10.  **如果此多播地址具有站点范围，则 ISCSITELOCAL():**返回 true。

    ```
    Syntax :public boolean isMCSiteLocal()
    ```

11.  **isMulticastAddress() :** 如果该地址是一个 IP 多播地址，则返回 true。多播地址的前 4 位是 1110。

    ```
    Syntax :public boolean isMulticastAddress()
    ```

12.  **如果该地址是站点本地地址，issitelocaddress():**返回 true。

    ```
    Syntax :public boolean isSiteLocalAddress()()
    ```

13.  **hashCode() :** 返回与此地址对象关联的 hashCode。

    ```
    Syntax : public int hashCode()
    ```

14.  **equals()** : returns true if this ip address is same as that of the object specified. Equals() method don’t consider host names while comparing and only consider IP address associated.

    ```
    Syntax : public boolean equals(Object obj)
    Parameters :
    obj : object to compare with
    ```

    ```
    // Java program to illustrate
    // Inetaddress class methods
    import java.net.Inet4Address;
    import java.net.InetAddress;
    import java.net.UnknownHostException;
    import java.util.Arrays;

    public class inetadd 
    {

        public static void main(String[] args) throws UnknownHostException 
            {

            String url = "www.geeksforgeeks.org";
            byte addr[]={127, 0, 0, 1};
            InetAddress ip1 =  Inet4Address.getByName(url);
            InetAddress ip2 =  InetAddress.getByAddress(addr);

            // Following methods checks the property of the thus created object.
            // getAddress() method
            System.out.println("Address : " + Arrays.toString(ip1.getAddress()));

            // getHostAddress() method
            System.out.println("Host Address : " + ip1.getHostAddress());

            // isAnyLocalAddress() method
            System.out.println("isAnyLocalAddress : " + ip1.isAnyLocalAddress());

            // isLinkLocalAddress() method
            System.out.println("isLinkLocalAddress : " + ip1.isLinkLocalAddress());

            // isLoopbackAddress() method
            System.out.println("isLoopbackAddress : " + ip1.isLoopbackAddress());

            // isMCGlobal() method
            System.out.println("isMCGlobal : " + ip1.isMCGlobal());

            // isMCLinkLocal() method
            System.out.println("isMCLinkLocal : " + ip1.isMCLinkLocal());

            // isMCNodeLocal() method
            System.out.println("isMCNodeLocal : " + ip1.isMCNodeLocal());

            // isMCOrgLocal() method
            System.out.println("isMCOrgLocal : " + ip1.isMCOrgLocal());

            // isMCSiteLocal() method
            System.out.println("isMCSiteLocal : " + ip1.isMCSiteLocal());

            // isMulticastAddress() method
            System.out.println("isMulticastAddress : " + ip1.isMulticastAddress());

            // isSiteLocalAddress() method
            System.out.println("isSiteLocalAddress : " + ip1.isSiteLocalAddress());

            // hashCode() method
            System.out.println("hashCode : " + ip1.hashCode());

            // equals() method
            System.out.println("ip1==ip2 : " + ip1.equals(ip2));
        }

    }
    ```

    **输出:**

    ```
    Address : [52, 84, 102, 90]
    Host Address : 52.84.102.90
    isAnyLocalAddress : false
    isLinkLocalAddress : false
    isLoopbackAddress : false
    isMCGlobal : false
    isMCLinkLocal : false
    isMCNodeLocal : false
    isMCOrgLocal : false
    isMCSiteLocal : false
    isMulticastAddress : false
    isSiteLocalAddress : false
    hashCode : 877946458
    ip1==ip2 : false

    ```

15.  **isReachable() :** Returns true if this address is reachable. ICMP echo requests are used if permission can be granted otherwise the host tries to make a TCP connection at port 7 of the destination. This method is used generally as a pre-condition in various programs, to avoid Host Unreachable exceptions in future.

    ```
    Syntax :public boolean isReachable(int timeout)
                        throws IOException
    Parameters :
    timeout : time after which the call aborts, resulting in false value.
    Throws :
    IOException : if network error occurs

    ```

    另一个重载的 isReachable()方法指定了检查可达性时要使用的网络接口，ttl 参数指定了回声数据包在退出网络之前的跳数。

16.  ```
    Syntax :public boolean isReachable(NetworkInterface netif,
                      int ttl,
                      int timeout)
                        throws IOException
    Parameters :
    netif : Network interface to use
    ttl : time to live in milliseconds
    timeout : time after which the call aborts, resulting in false value.
    Throws :
    IOException : if network error occurs

    ```

17.  **获取主机名():**返回该 IP 地址的主机名。如果创建此对象时使用的主机名不同于返回的主机名，则执行反向查找以返回系统配置的主机名。

    ```
    Syntax :public String getHostName()
    ```

18.  **getCanonicalHostName() :** 返回此对象的完全限定域名。如果创建此对象时使用的主机名不同于返回的主机名，则执行反向查找以返回系统配置的主机名。

    ```
    Syntax :public String getCanonicalHostName()
    ```

19.  **toString() :** 将 IP 地址转换为字符串。它将结果作为主机名/ IP 地址返回。

    ```
    Syntax :public String toString()
    ```

20.  **getByAddress() :** One of the static methods to create an InetAddress object. It takes host name and IP address as its parameter. Host name can be the machine name as in “www.geeksforgeeks.org” or its textual IP address.

    ```
    Syntax : public static InetAddress getByAddress(String host,
                           byte[] addr)
                                    throws UnknownHostException
    Parameters :
    host : hostname
    addr : byte address for this object
    Throws :
    UnknownHostException : if IP address is of illegal length
    ```

    另一个重载方法，只接受字节地址，没有主机名。它只返回带有这个原始 IP 地址的 InetAddress 对象。

21.  ```
    Syntax : public static InetAddress getByAddress(byte[] addr)
                                    throws UnknownHostException
    Parameters :
    host : hostname
    addr : byte address for this object
    Throws :
    UnknownHostException : if IP address is of illegal length
    ```

22.  **getByName() :** 返回指定主机的 IP 地址。如果主机是一个字面上的 IP 地址，那么只检查其有效性。

    ```
    Syntax :public static InetAddress getByName(String host)
    Parameters :
    host : host name
    ```

23.  **getAllByName() :** 返回给定主机的 IP 地址数组。

    ```
    Syntax :public static InetAddress[] getAllByName(String host)
    Parameters :
    host : host name
    ```

24.  **getLoopbackAddress() :** 返回环回地址。

    ```
    Syntax :public static InetAddress getLoopbackAddress()

    ```

25.  **getLocalHost() :** Returns the IP address of the local host.

    ```
    Syntax :public static InetAddress getLocalHost()
                                    throws UnknownHostException
    Throws :
    UnknownHostException : If local host cannot be resolved into an address

    ```

    ```
    // Java program to illustrate
    // Inetaddress class methods
    import java.io.IOException;
    import java.net.InetAddress;
    import java.util.Arrays;

    public class inetadd2 
    {
        public static void main(String[] args) throws IOException 
        {

            String url = "www.geeksforgeeks.org";
            byte addr[] = { 127, 0, 0, 1 };

            // getByName() method
            InetAddress ip1 = InetAddress.getByName(url);
            System.out.println("getByName() : " + ip1);

            // getByAddress() method
            InetAddress ip2 = InetAddress.getByAddress(addr);
            System.out.println("getByAddress() : " + ip2);

            // getLocalHost() method
            InetAddress ip3 = InetAddress.getLocalHost();
            System.out.println("getLocalHost() : " + ip3);

            // getLoopbackAddress() method
            InetAddress ip4 = InetAddress.getLoopbackAddress();
            System.out.println("getLoopbackAddress() : " + ip4);

            // getAllByName() method - returns all ip addresses
            // associated with google.com
            InetAddress addrs[] = InetAddress.getAllByName("www.google.com");
            System.out.println("Google ip addresses : " + Arrays.toString(addrs));

            // isReachable() method
            boolean isreach = ip1.isReachable(50);
            System.out.println("ip1 isReachable() : " + isreach);

            // getHostname() method
            String hostname = ip1.getHostName();
            System.out.println("ip1 hostname :" + hostname);

            // getCanonicalHostname() method
            System.out.println("ip1 CanonicalHostname : " + ip1.getCanonicalHostName());

            // toString() method
            System.out.println("ip1 toString() : " + ip1.toString());
        }
    }
    ```

    **输出:**

    ```
    getByName() : www.geeksforgeeks.org/52.84.102.90
    getByAddress() : /127.0.0.1
    getLocalHost() : DESKTOP-K4GGDH6/192.168.1.5
    getLoopbackAddress() : localhost/127.0.0.1
    Google ip addresses : [www.google.com/216.58.199.132]
    ip1 isReachable() : false
    ip1 hostname :www.geeksforgeeks.org
    ip1 CanonicalHostname : server-52-84-102-90.del51.r.cloudfront.net
    ip1 toString() : www.geeksforgeeks.org/52.84.102.90

    ```

下面的程序使用 InetAddress 类来获取给定域名的 IP 地址。当程序在连接到互联网的系统上运行时，它会给出给定域的 IP 地址。

```
// A Java program to demonstrate working of InetAddress class
// This program finds IP address for a domain name.
import java.net.*;

public class GetIPAddress
{
    public static void main(String args[]) throws Exception
    {
        String url = "www.google.com";
        try
        {
            // Get IP addresses related to the domain
            InetAddress ips[] = InetAddress.getAllByName(url);

            // Display ip addresses
            System.out.println("IP Address(es)");
            for (InetAddress addr:ips)
                System.out.println(addr.getHostAddress());
        }
        catch(Exception ex)
        {
            System.out.println("host not found");
        }
    }
}
```

**输出:**

```
IP Address(es)
172.217.4.68
2607:f8b0:4006:809:0:0:0:2004
```

参考资料:
[官方 Java 文档](https://docs.oracle.com/javase/7/docs/api/java/net/InetAddress.html)

本文由**里沙布·马赫塞和阿帕娜·瓦德拉马尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。