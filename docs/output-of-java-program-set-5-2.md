# Java 程序输出|第 5 集

> 原文:[https://www . geesforgeks . org/output-of-Java-program-set-5-2/](https://www.geeksforgeeks.org/output-of-java-program-set-5-2/)

预测以下 Java 程序的输出。
**节目 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Main.java
public class Main
{
    public static void gfg(String s)
    {    
        System.out.println("String");
    }
    public static void gfg(Object o)
    {
        System.out.println("Object");
    }

    public static void main(String args[])
    {
        gfg(null);
    }
} //end class
```

**输出**:

```java
String
```

**说明**:在[方法重载](https://www.geeksforgeeks.org/overloading-in-java/)的情况下，编译时选择最具体的方法。因为“java.lang.String”是比“java.lang.Object”更具体的类型。在这种情况下，选择“字符串”作为参数的方法。
**程序二:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Main.java
public class Main
{
    public static void gfg(String s)
    {    
        System.out.println("String");
    }
    public static void gfg(Object o)
    {
        System.out.println("Object");
    }
    public static void gfg(Integer i)
    {
        System.out.println("Integer");
    }

    public static void main(String args[])
    {
        gfg(null);
    }
} //end class
```

**输出:**

```java
Compile Error at line 19.
```

**说明:**在这种[方法重载](https://www.geeksforgeeks.org/overloading-in-java/)的情况下，编译时选择最具体的方法。
由于“java.lang.String”和“java.lang.Integer”是比“java.lang.Object”更具体的类型，但在“java.lang.String”和“java.lang.Integer”之间没有更具体的。
在这种情况下，Java 无法决定调用哪个方法。
**程序 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Main.java
public class Main
{
    public static void main(String args[])
    {
        String s1 = "abc";
        String s2 = s1;
        s1 += "d";
        System.out.println(s1 + " " + s2 + " " + (s1 == s2));

        StringBuffer sb1 = new StringBuffer("abc");
        StringBuffer sb2 = sb1;
        sb1.append("d");
        System.out.println(sb1 + " " + sb2 + " " + (sb1 == sb2));
    }
} //end class
```

输出:

```java
abcd abc false
abcd abcd true
```

**说明:**在 Java 中，String 是不可变的，string buffer 是可变的。
所以字符串 s2 和 s1 都指向同一个字符串 abc。并且，在进行更改后，字符串 s1 指向 abcd，s2 指向 abc，因此为 false。在字符串缓冲区中，sb1 和 sb2 都指向同一个对象。由于字符串缓冲区是可变的，因此对一个字符串进行更改也会对另一个字符串进行更改。因此，在对对象进行更改后，两个字符串仍然指向同一个对象(这里是 sb2)。
**程序 4:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Main.java
public class Main
{
    public static void main(String args[])
    {
        short s = 0;
        int x = 07;
        int y = 08;
        int z = 112345;

        s += z;
        System.out.println("" + x + y + s);
    }
} //end class
```

**输出:**

```java
Compile Error at line 8
```

**说明:**
1。在第 12 行中，println 中的“”使数字自动转换为字符串。所以它不做加法，而是作为字符串一起追加。
2。在第 11 行中+=自动转换为短整型。然而，数字 123456 不能包含在一个短整型数中，因此最终会出现负值(-7616)。
(注-短 2 字节-32，768 到 32，767)，这里的数字 123456 并不是指 int z 的值，而是显示 int 值的长度
3。然而，另外两个是转移注意力的，因为由于第 8 行的原因，代码永远不会编译。
任何以零开始的数字都被视为八进制数(0-7)。
本文由 [**Pratik Agarwal**](https://www.facebook.com/Pratik.Agarwal01) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。