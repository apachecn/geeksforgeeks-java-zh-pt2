# Java 中的 URL getFile()方法，带示例

> 原文:[https://www . geesforgeks . org/URL-getfile-method-in-Java-with-examples/](https://www.geeksforgeeks.org/url-getfile-method-in-java-with-examples/)

getFile()函数是 URL 类的一部分。函数 getFile()返回指定网址的文件名。函数的作用是:返回网址的路径和查询。

**功能签名**:

```java
public String getFile()
```

**语法**:

```java
url.getFile()
```

**参数**:该功能不需要任何参数

**返回类型:**函数返回字符串类型

下面程序说明了 getFile()函数的使用:

**示例 1** :给定一个 URL，我们将使用 getFile()函数获取文件。

```java
// Java program to show the
// use of the function getFile()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {

            // create a URL
            url = new URL(
                "https:// www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples/");

            // get the  File
            String _File = url.getFile();

            // display the URL
            System.out.println("URL = " + url);

            // display the  File
            System.out.println(" File= " + _File);
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

```java
URL = https:// www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples/
 File= /url-getprotocol-method-in-java-with-examples/

```

**例 2** :现在看看 getFile()和 getPath()有什么不同。getPath()将排除该查询，但 getFile()将包括该查询

```java
// Java program to show the
// use of the function getFile()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {

            // create a URL
            url = new URL(
                "https:// www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples?title=protocol");

            // get the  File
            String _File = url.getFile();

            // display the URL
            System.out.println("URL = " + url);

            // display the  File
            System.out.println(" File= " + _File);
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

```java
URL = https:// www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples?title=protocol
 File= /url-getprotocol-method-in-java-with-examples?title=protocol

```