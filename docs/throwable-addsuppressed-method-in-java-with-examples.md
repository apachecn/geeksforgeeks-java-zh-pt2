# Java 中可抛出的 addSuppressed()方法，示例

> 原文:[https://www . geesforgeks . org/throwable-addsuppressed-method-in-Java-with-examples/](https://www.geeksforgeeks.org/throwable-addsuppressed-method-in-java-with-examples/)

**添加抑制？(可抛出异常)**可抛出类的方法，用于将异常附加到为了传递该异常而被抑制的异常。这个方法是线程安全的方法。此方法通常由 try-catch 子句调用。除非通过构造函数禁用，否则可投掷对象的抑制行为是启用的。当抑制被禁用时，此方法除了验证其参数之外什么也不做。
在 try-finally 块的默认行为中，我们有两个异常，原始异常被抑制，来自 finally 块的异常被显示。在某些情况下，使用 finally block 来关闭资源，在这种情况下，我们希望看到原始异常，以及来自 finally block 的一些异常，这些异常关闭了我们的资源并失败了，因此我们可以添加那些通过此方法抑制的异常。
如果有多个兄弟异常，并且只能传播一个，那么这个方法可以用来传播那个方法。
**语法:**

```
public final void addSuppressed?(Throwable exception)
```

**参数:**这个方法只接受一个参数**异常**，我们想把它作为一个被抑制的异常加入。
**返回:**此方法不返回任何内容。
**异常:**此方法抛出以下异常:

*   IllegalArgumentException:如果这个异常是可抛出的；可投掷的不能抑制自己。
*   NullPointerException:如果异常为 null。

下面的程序说明了添加抑制？()方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the addSuppressed() Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {

        try {

            testException();
        }

        catch (Throwable e) {

            // get StackTraceElements
            Throwable[] suppExe
                = e.getSuppressed();

            // print element of suppExe
            for (int i = 0; i < suppExe.length; i++) {

                System.out.println("Suppressed Exceptions:");
                System.out.println(suppExe[i]);
            }
        }
    }

    // method which throws Exception
    public static void testException()
        throws Exception
    {

        // creating a suppressed Exception
        Exception
            suppressed
            = new ArithmeticException();

        // creating a IOException object
        final Exception exe = new Exception();

        // adding suppressed Exception
        // using addSuppressed method
        exe.addSuppressed(suppressed);

        // throwing IOException
        throw exe;
    }
}
```

**Output:** 

```
Suppressed Exceptions:
java.lang.ArithmeticException
```