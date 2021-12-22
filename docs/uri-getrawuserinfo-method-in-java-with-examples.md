# Java 中的 URI getRawUserInfo()方法，带示例

> 原文:[https://www . geesforgeks . org/uri-getrawuserinfo-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uri-getrawuserinfo-method-in-java-with-examples/)

函数是 URI 类的一部分。函数 getRawUserInfo()返回指定 URI 的原始用户信息部分。该函数返回用户信息的精确值，而不解码转义八位字节序列(如果有)。

**功能签名:**

```
public String getRawUserInfo()
```

**语法**:

```
uri.getRawUserInfo()
```

**参数**:该函数不需要任何参数
**返回类型:**函数返回字符串类型

下面的程序说明了 getUserInfo()函数的使用:

**示例 1:** 给定一个 URI，我们将使用 getRawUserInfo()函数获取用户信息。

```
// Java program to show the
// use of the function getRawUserInfo()

import java.net.*;
class Solution {
    public static void main(String args[])
    {
        // uri  object
        URI uri = null;

        try {
            // create a URI
            uri = new URI("https://Arnab_Kundu@www.geeksforgeeks.org");

            // get the  Raw UserInfo
            String Raw_UserInfo = uri.getRawUserInfo();

            // display the URI
            System.out.println("URI = " + uri);

            // display the  UserInfo
            System.out.println(" Raw UserInfo="
                               + Raw_UserInfo);
        }
        // if any error occurs
        catch (URISyntaxException e) {
            // display the error
            System.out.println("URL Exception ="
                               + e.getMessage());
        }
    }
}
```

**Output:**

```
URI = https://Arnab_Kundu@www.geeksforgeeks.org
 Raw UserInfo=Arnab_Kundu

```

**示例 2:**getuserninfo()和 getRawUserInfo()返回的值是相同的，只是转义八位字节的所有序列都被解码。getRawUserInfo()返回用户提供的字符串的确切值，但 getUserInfo()函数解码转义八位字节序列(如果有)。

```
// Java program to show the
// use of the function getRawUserInfo()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // uri  object
        URI uri = null;

        try {
            // create a URI
            uri = new URI("https://Arnab_Kundu%E2%82%AC@www.geeksforgeeks.org");

            // get the  UserInfo
            String _UserInfo = uri.getUserInfo();

            // get the  Raw UserInfo
            String Raw_UserInfo = uri.getRawUserInfo();

            // display the URI
            System.out.println("URI = " + uri);

            // display the  UserInfo
            System.out.println(" UserInfo=" + _UserInfo);

            // display the  UserInfo
            System.out.println(" Raw UserInfo=" + Raw_UserInfo);
        }
        // if any error occurs
        catch (URISyntaxException e) {
            // display the error
            System.out.println("URL Exception =" + e.getMessage());
        }
    }
}
```

**Output:**

```
URI = https://Arnab_Kundu%E2%82%AC@www.geeksforgeeks.org
 UserInfo=Arnab_Kundu?
 Raw UserInfo=Arnab_Kundu%E2%82%AC

```