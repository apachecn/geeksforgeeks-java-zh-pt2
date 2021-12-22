# Java 中的 URL getHost()方法，带示例

> 原文:[https://www . geesforgeks . org/URL-gethost-method-in-Java-with-examples/](https://www.geeksforgeeks.org/url-gethost-method-in-java-with-examples/)

**getHost()** 功能是 [URL 类](https://www.geeksforgeeks.org/url-class-java-examples/)的一部分。函数 getHost()返回指定网址的主机。网址的主机部分是网址的主机名。主机的格式符合 RFC 2732。

**功能签名**

```
public String getHost()

```

**语法**

```
url.getHost()

```

**参数**:该功能不需要任何参数

**返回类型**:函数返回**字符串**类型

下面程序说明了 getHost()函数的使用:

**例 1:**

```
// Java program to show the use
// of the function getHost()

import java.net.*;

class GFG {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {

            // create a URL
            url
                = new URL("https:// www.geeksforgeeks.org");

            // get the Host
            String Host = url.getHost();

            // display the URL
            System.out.println("URL = " + url);

            // display the Host
            System.out.println("Host = " + Host);
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
Host =  www.geeksforgeeks.org

```

**例 2:**

```
// Java program to show the
// use of the function getHost()

import java.net.*;

class GFG {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {
            // create a URL
            url
                = new URL(
                    "https:// www.geeksforgeeks.org:80/url-samefile-method-in-java-with-examples/");

            // get the Authority
            String authority
                = url.getAuthority();

            // get the Host
            String host = url.getHost();

            // display the URL
            System.out.println("URL = " + url);

            // display the Host
            System.out.println("Authority = "
                               + authority);

            // display the Host
            System.out.println("Host = " + host);
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
URL = https:// www.geeksforgeeks.org:80/url-samefile-method-in-java-with-examples/
Authority =  www.geeksforgeeks.org:80
Host =  www.geeksforgeeks.org

```

**示例 3:** 如果我们创建一个没有主机名的 URL，并使用 getHost()函数请求主机，则该函数返回空字符串。

```
// Java program to show the
// use of the function getHost()

import java.net.*;

class GFG {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {
            // create a URL
            url = new URL("https://");

            // get the Host
            String Host = url.getHost();

            // display the URL
            System.out.println("URL = " + url);

            // display the Host
            System.out.println("Host = " + Host);
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
URL = https:
Host =

```