# Java(JVM)中的验证

> 原文:[https://www.geeksforgeeks.org/verification-java-jvm/](https://www.geeksforgeeks.org/verification-java-jvm/)

在 [JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 中的类装入器装入的字节码后。字节码首先被验证器检查有效性，这个过程被称为**验证**。验证器在链接时执行尽可能多的检查，以便消除解释器在运行时执行的昂贵操作。它提高了翻译的性能。

**验证者执行的一些检查:**

*   未初始化的变量
*   不违反私有数据和方法的访问规则。
*   方法调用与对象引用匹配。
*   没有操作数堆栈溢出或下溢。
*   所有 Java 虚拟机指令的参数都是有效的类型。
*   确保最终类不被子类化，并且最终方法不被覆盖
*   检查所有字段引用和方法引用是否具有有效的名称、有效的类和有效的类型描述符。([来源](https://docs.oracle.com/javase/specs/jvms/se7/html/jvms-4.html#jvms-4.10))

如果这些检查中的任何一个失败，JVM 都会抛出一个“java.lang.VerifyError”错误。但是，我们可以使用禁用这些检查

```
java -noverify VerifyGeekFile

```

人们可能会想，既然编译器在生成之前会检查上述验证，那么程序是如何被操作的。类文件。但是类文件在 JVM 加载之前很容易被更改。类文件中使用的字节码被很好地记录了下来，对十六进制有一些了解的人可以在。类文件从而改变程序的行为。
例如:网络浏览器中的小程序不下载源代码，而是下载预编译的类文件。您计算机上的浏览器决定了这个类文件是否值得运行，或者该文件是否被“恶意编译器”利用。

考虑这个简单的程序

```
// A Java program to demonstrate working
// of the verification process

class VerifyGeekFile
{
    // your initial bank bal
    private float bal;

    // Method to deposit money
    float depositBalance(int bal)
    {
        int myBal = bal;
        this.bal += myBal;
        return this.bal;
    }

    // Driver Method
    public static void main(String[] args)
    {
        VerifyGeekFile obj = new VerifyGeekFile();
        System.out.println(obj.depositBalance(4000));
    }
}
```

```
Output
 4000.0

```

然后在命令行中执行该命令，以助记符的形式查看字节码:-

```
javap -c VerifyGeekFile

```

输出:

```
float depositBalance(int);
    Code:
       0: iload_1
       1: istore_2
       2: aload_0
       3: dup
       4: getfield      #2                  // Field bal:F
       7: iload_2
       8: i2f
       9: fadd
      10: putfield      #2                  // Field bal:F
      13: aload_0
      14: getfield      #2                  // Field bal:F
      17: freturn

```

在这里，如果我们使用十六进制编辑器更改 myBal 的初始值或保持其未初始化，将返回意外的结果。Java 验证过程保护我们免受所有这些陷阱。

**参考文献:**
[http://www.informit.com/articles/article.aspx?p=1187967&seqNum = 2](http://www.informit.com/articles/article.aspx?p=1187967&seqNum=2)
[https://docs . Oracle . com/javase/specs/JVMs/se7/html/JVMs-4 . html # JVMs-4.10](https://docs.oracle.com/javase/specs/jvms/se7/html/jvms-4.html#jvms-4.10)