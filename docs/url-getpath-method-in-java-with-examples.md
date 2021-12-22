# Java 中的 URL getPath()方法，带示例

> 原文:[https://www . geesforgeks . org/URL-get path-method-in-Java-with-examples/](https://www.geeksforgeeks.org/url-getpath-method-in-java-with-examples/)

**getPath()** 函数是 **URL 类**的一部分。函数 getPath()返回指定网址的路径名。

**功能签名**:

```java
public String getPath()
```

**语法**:

```java
url.getPath()
```

**参数**:该函数不需要任何参数
**返回类型:**函数返回字符串类型

下面的程序说明了 getPath()函数的使用:

**示例 1** :给定一个 URL，我们将使用 getPath()函数获取路径。

```java
// Java program to show the
// use of the function getPath()

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

            // get the  Path
            String _Path = url.getPath();

            // display the URL
            System.out.println("URL = " + url);

            // display the  Path
            System.out.println(" Path= " + _Path);
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
 Path= /url-getprotocol-method-in-java-with-examples/

```

**例 2** :现在看看 getPath()和 getFile()有什么不同。getPath()将排除该查询，但 getFile()将包括该查询

```java
// Java program to show the
// use of the function getPath()

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

            // get the  Path
            String _Path = url.getPath();

            // display the URL
            System.out.println("URL = " + url);

            // display the  Path
            System.out.println(" Path= " + _Path);
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
 Path= /url-getprotocol-method-in-java-with-examples

```