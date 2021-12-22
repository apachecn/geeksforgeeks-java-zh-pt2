# Java 中的 URL getUserInfo()方法，带示例

> 原文:[https://www . geesforgeks . org/URL-getuser info-method-in-Java-with-examples/](https://www.geeksforgeeks.org/url-getuserinfo-method-in-java-with-examples/)

**getUserInfo()** 函数是 **URL 类**的一部分。函数 getUserInfo()返回指定网址的用户信息部分。

**功能签名**:

```java
public String getUserInfo()
```

**语法**:

```java
url.getUserInfo()
```

**参数**:该功能不需要任何参数

**返回类型:**函数返回字符串类型

下面的程序说明了 getUserInfo()函数的使用:

**示例 1** :给定一个 URL，我们将使用 getUserInfo()函数获取 UserInfo。

```java
// Java program to show the use
// of the function getUserInfo()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {
            // create a URL
            url = new URL(
                "https:// Arnab_Kundu@www.geeksforgeeks.org");

            // get the  UserInfo
            String _UserInfo = url.getUserInfo();

            // display the URL
            System.out.println("URL = " + url);

            // display the  UserInfo
            System.out.println(" UserInfo= "
                               + _UserInfo);
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
URL = https:// Arnab_Kundu@www.geeksforgeeks.org
 UserInfo=  Arnab_Kundu

```

**示例 2** :现在我们不提供任何用户信息，使用函数获取用户信息并查看结果。

```java
// Java program to show the use
// of the function getUserInfo()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {
            // create a URL
            url = new URL("https:// www.geeksforgeeks.org");

            // get the  UserInfo
            String _UserInfo = url.getUserInfo();

            // display the URL
            System.out.println("URL = " + url);

            // display the  UserInfo
            System.out.println(" UserInfo= "
                               + _UserInfo);
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
URL = https:// www.geeksforgeeks.org
 UserInfo= null

```