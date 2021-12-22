# Java 中的 URL sameFile()方法，带示例

> 原文:[https://www . geesforgeks . org/URL-same file-method-in-Java-with-examples/](https://www.geeksforgeeks.org/url-samefile-method-in-java-with-examples/)

[Java.net.URL 类](https://www.geeksforgeeks.org/url-class-java-examples/)的 **sameFile()** 函数用于比较除片段部分之外的两个 URL。如果两个网址相同(不包括片段部分)，则该方法返回真，否则返回假。

**功能签名**

```java
public boolean sameFile(URL u)

```

**语法**

```java
url1.sameFile(url2);

```

**参数:**此方法接受一个强制参数 **url** ，这是要与此 url 进行比较的第二个 url。

**返回值:**如果除片段部分外两个网址相同，则该方法返回真，否则返回假。

下面的方法说明了 URL.sameFile()方法:

**例 1:**

```java
// Java program to illustrate
// URL.sameFile() method

import java.net.*;

class GFG {
    public static void main(String args[]) throws Exception
    {

        // create URL1
        URL url1
            = new URL("https:// www.geeksforgeeks.org");

        // create URL2
        URL url2
            = new URL("https:// www.geeksforgeeks.org");

        // check if two URL are same or not
        System.out.print("URL 1 is compared to URL 2: ");

        if (url1.sameFile(url2))
            System.out.println("same");
        else
            System.out.println("not same");
    }
}
```

**输出:**

```java
URL 1 is compared to URL 2: same

```

**示例 2:**same file()函数有一个特殊的用法，使其不同于 equals()函数。函数的作用是:比较除片段部分之外的网址。下面的例子将说明它不同于 equals 函数的用法。

```java
// Java program to check the use of sameFile

import java.net.*;

class GFG {
    public static void main(String args[]) throws Exception
    {
        // create URL1
        URL url1
            = new URL("https:// www.geeksforgeeks.org");

        // create URL2
        URL url2
            = new URL("https:// www.geeksforgeeks.org#print");

        // check if two URL are same or not
        System.out.print("URL 1 is compared to URL 2: ");

        if (url1.sameFile(url2))
            System.out.println("same");
        else
            System.out.println("not same");
    }
}
```

**输出:**

```java
URL 1 is compared to URL 2: same

```

**注意:**如果使用了 equals 函数，那么第二个代码会打印“不相同”，但是使用 sameFile()函数会给出“相同”的结果。