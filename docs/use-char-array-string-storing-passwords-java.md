# 为什么在 Java 中用 char[]数组代替字符串来存储密码？

> 原文:[https://www . geesforgeks . org/use-char-array-string-storing-password-Java/](https://www.geeksforgeeks.org/use-char-array-string-storing-passwords-java/)

**1。字符串是不可变的:**字符串在 Java 中是不可变的，因此如果密码以纯文本形式存储，它将在内存中可用，直到垃圾收集器清除它，并且由于字符串在字符串池中用于重用，它很有可能会在内存中保留很长时间，这是一个安全威胁。字符串是不可变的，字符串的内容不可能改变，因为任何改变都会产生新的字符串。
有了数组，数据可以在其工作完成后显式地擦除数据。该数组可以被覆盖，并且密码不会出现在系统的任何地方，甚至在垃圾收集之前。

**2。安全性:**任何可以访问内存转储的人都可以用明文找到密码，这是使用加密密码而不是明文的另一个原因。因此，将密码存储在字符数组中显然可以降低窃取密码的安全风险。

**3。日志文件安全:**有了数组，就可以显式的擦除数据，覆盖数组，密码在系统的任何地方都不会出现。
使用普通字符串，不小心将密码打印到日志、监视器或其他不安全的地方的可能性要高得多。char[]不太容易受到攻击。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
//Java program to illustrate preferring char[] arrays
//over strings for passwords in Java
public class PasswordPreference
{

    public static void main(String[] args)
    {

        String strPwd = "password";
        char[] charPwd = new char[] {'p','a','s','s','w','o','r','d'};

        System.out.println("String password: " + strPwd );
        System.out.println("Character password: " + charPwd );
    }
}
```

**输出:**

```java
String password: password
Character password: [C@15db9742
```

**4。Java 推荐:** Java 有像 javax.swing 的 JPasswordField 这样的方法作为方法返回 String 的 public String getText()在 Java 2 中被弃用，被返回 Char Array 的 public char[] getPassword()所代替。

本文由 **Kanika Tyagi** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如发现任何不正确的地方，请写评论，或者您想分享更多关于上述话题的信息