# Java 中的 URL getPort()方法，带示例

> 原文:[https://www . geesforgeks . org/URL-getport-method-in-Java-with-examples/](https://www.geeksforgeeks.org/url-getport-method-in-java-with-examples/)

**getPort()** 功能是 [URL 类](https://www.geeksforgeeks.org/url-class-java-examples/)的一部分。函数 getPort()返回指定网址的端口。如果未设置端口，该函数将返回端口号或-1

**功能签名**

```
public int getPort()

```

**语法**

```
url.getPort()

```

**返回类型**:函数返回**整数**类型

**参数**:该功能不需要任何参数

下面的程序说明了 getPort()函数的使用:

**示例 1**
显示指定网址的端口

```
// Java program to show the use of the function getPort()
import java.net.*;
class Solution {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {
            // create a URL
            url = new URL("https:// www.geeksforgeeks.org:80");

            // get the  port
            int _port = url.getPort();

            // display the URL
            System.out.println("URL = " + url);

            // display the  port
            System.out.println(" Port=" + _port);
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
URL = https:// www.geeksforgeeks.org:80
 Port=80

```

**示例 2:** 创建一个没有定义端口的 URL，然后尝试使用 getPort()函数获取端口。

```
// Java program to show the
// use of the function getPort()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // url object
        URL url = null;

        try {
            // create a URL
            url = new URL("https:// www.geeksforgeeks.org");

            // get the port
            int _port = url.getPort();

            // display the URL
            System.out.println("URL = " + url);

            // display the port
            System.out.println(" Port=" + _port);
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
 Port=-1

```