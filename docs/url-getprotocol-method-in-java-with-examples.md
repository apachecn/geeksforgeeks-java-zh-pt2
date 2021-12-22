# Java 中的 URL getProtocol()方法，带示例

> 原文:[https://www . geesforgeks . org/URL-get protocol-method-in-Java-with-examples/](https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples/)

**getProtocol()** 函数是 [URL 类](https://www.geeksforgeeks.org/url-class-java-examples/)的一部分。函数 getProtocol()返回指定网址的协议。

**功能签名**

```
public String getProtocol()

```

**语法**

```
url.getProtocol()

```

**参数**该功能不需要任何参数

**返回类型**:函数返回**字符串**类型

下面的程序说明了 getProtocol()函数的使用:

**例 1:**

```
// Java program to show the
// use of the function getProtocol()

import java.net.*;

class GFG {
    public static void main(String args[])
    {
        // url object
        URL url = null;

        try {
            // create a URL
            url = new URL("https:// www.geeksforgeeks.org");

            // get the Protocol
            String Protocol = url.getProtocol();

            // display the URL
            System.out.println("URL = " + url);

            // display the Protocol
            System.out.println("Protocol = " + Protocol);

            // create a URL
            url = new URL("http:// www.geeksforgeeks.org");

            // get the Protocol
            Protocol = url.getProtocol();

            // display the URL
            System.out.println("URL = " + url);

            // display the Protocol
            System.out.println("Protocol = " + Protocol);

            // create a URL
            url = new URL("ftp:// www.geeksforgeeks.org");

            // get the Protocol
            Protocol = url.getProtocol();

            // display the URL
            System.out.println("URL = " + url);

            // display the Protocol
            System.out.println("Protocol = " + Protocol);
        }

        // if any error occurs
        catch (Exception e) {

            // display the error
            System.out.println(e);
        }
    }
}
```

**Output:**

```
URL = https:// www.geeksforgeeks.org
Protocol = https
URL = http:// www.geeksforgeeks.org
Protocol = http
URL = ftp:// www.geeksforgeeks.org
Protocol = ftp

```