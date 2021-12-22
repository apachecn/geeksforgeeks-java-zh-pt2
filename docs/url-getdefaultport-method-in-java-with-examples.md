# Java 中的 URL getDefaultPort()方法，带示例

> 原文:[https://www . geesforgeks . org/URL-getdefaultport-method-in-Java-with-examples/](https://www.geeksforgeeks.org/url-getdefaultport-method-in-java-with-examples/)

[URL 类](https://www.geeksforgeeks.org/url-class-java-examples/)的 **getDefaultPort()** 函数返回指定 URL 的默认端口。如果 URL 方案或 URL 的 URL 流处理程序没有定义默认端口号，则该函数返回-1。

**功能签名**

```
public int getDefaultPort()

```

**语法**

```
url.getDefaultPort()

```

**参数**该功能不需要任何参数

**返回值**:该函数返回**一个整数值**，它是指定网址的默认端口。

下面的例子将说明 getDefaultPort()函数的使用:

**例 1**HTTPS 默认港口

```
// Java program to show the use
// of the function getDefaultPort()

import java.net.*;

class GFG {
    public static void main(String args[])
    {

        // url  object
        URL url = null;

        try {

            // create a URL
            url = new URL("https:// www.geeksforgeeks.org");

            // get the default port
            int default_port = url.getDefaultPort();

            // display the URL
            System.out.println("URL: " + url);

            // display the default port
            System.out.println("Default Port: "
                               + default_port);
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
URL: https:// www.geeksforgeeks.org
Default Port: 443

```

**示例 2:**HTTP 的默认端口

```
// Java program to show the use
// of the function getDefaultPort()

import java.net.*;

class GFG {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {
            // create a URL
            url = new URL("http:// www.geeksforgeeks.org");

            // get the default port
            int default_port = url.getDefaultPort();

            // display the URL
            System.out.println("URL: " + url);

            // display the default port
            System.out.println("Default Port: "
                               + default_port);
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
URL: http:// www.geeksforgeeks.org
Default Port: 80

```

**例 3**FTP 默认端口

```
// Java program to show the use
// of the function getDefaultPort()

import java.net.*;

class GFG {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {

            // create a URL
            url = new URL("ftp:// www.geeksforgeeks.org");

            // get the default port
            int default_port = url.getDefaultPort();

            // display the URL
            System.out.println("URL: " + url);

            // display the default port
            System.out.println("Default Port: "
                               + default_port);
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
URL: ftp:// www.geeksforgeeks.org
Default Port: 21

```