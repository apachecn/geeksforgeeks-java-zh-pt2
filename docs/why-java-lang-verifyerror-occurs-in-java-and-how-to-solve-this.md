# Java 中为什么会出现 java.lang.VerifyError，如何解决？

> 原文:[https://www . geesforgeks . org/why-Java-lang-verify error-in-Java-occurs-and-how-solution-this/](https://www.geeksforgeeks.org/why-java-lang-verifyerror-occurs-in-java-and-how-to-solve-this/)

Java 虚拟机(JVM)不信任所有加载的字节码，这是 Java 安全模型的核心原则。在运行时，JVM 将加载。类文件，并试图将它们链接在一起形成一个可执行文件——但这些加载的有效性。类文件未知。以确保装载。类文件不会对最终的可执行文件构成威胁，验证过程是在。类文件。

此外，JVM 确保二进制文件格式良好。例如，JVM 将验证类不包含最终类。在许多情况下，验证在有效的、非恶意的字节码上失败，因为较新版本的 Java 比旧版本有更严格的验证过程。例如，JDK 13 可能添加了一个在 JDK 7 中未强制实施的验证步骤。因此，如果我们用 JVM 13 运行一个应用程序，并包含用旧版本的 Java 编译器(javac)编译的依赖项，JVM 可能会认为过时的依赖项是无效的。

因此，当链接老。类文件，JVM 可能会抛出一个 java.lang.VerifyError。

验证错误从 1.0 版本的 Java 开始就存在了。

**验证错误的结构:**

**施工方**T0

此构造函数创建 VerifyError 类的实例，将 null 设置为其消息。

```java
VerifyError(String s)
```

此构造函数使用指定的字符串作为消息，创建 VerifyError 类的实例。这里抛出错误的类是通过字符串参数指示的。

**出现此错误的三个最常见原因如下:**

**原因 1:** “每当一个声明为 final 的类被扩展时，就会抛出这个错误。”

**程序:**

## 爪哇

```java
// Java program to show the occurence 
// of  java.lang.VerifyError

class B extends A {

    public static void main(String args[])

    {

        System.out.println("my super class name:-"
                           + myname);
    }
}

public class A

{

    static String myname = "A";
}
```