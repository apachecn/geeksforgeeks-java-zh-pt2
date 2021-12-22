# Java 中的可抛出类，示例

> 原文:[https://www . geeksforgeeks . org/throwable-class-in-Java-with-examples/](https://www.geeksforgeeks.org/throwable-class-in-java-with-examples/)

[类和对象](https://www.geeksforgeeks.org/classes-objects-java/)是[面向对象编程](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/)的基本概念，围绕现实实体展开。类是用户定义的蓝图或原型，从中创建对象。它表示一种类型的所有对象共有的一组属性或方法。在本文中，我们将讨论**可抛出的**类，它的构造函数和这个类中可用的不同方法。

**Throwable** 类是 Java 语言中每个错误和异常的超类。只有属于该类子类之一的对象才会被任何“Java 虚拟机”抛出，或者可能被 Java throw 语句抛出。为了在编译时检查异常的动机，**可抛出的**和可抛出的任何子类，如果不是 Error 或 RuntimeException 的子类，都被认为是[检查的异常](https://www.geeksforgeeks.org/checked-vs-unchecked-exceptions-in-java/)。

可抛出类是 Java [异常层次](https://www.geeksforgeeks.org/exceptions-in-java/)的根类，由两个子类继承:

1.例外

2.错误

可抛出类实现[可串行化接口](https://www.geeksforgeeks.org/marker-interface-java/)，直接已知的可抛出类是[错误和异常。](https://www.geeksforgeeks.org/errors-v-s-exceptions-in-java/)

Throwable 包含其线程在创建时的执行堆栈快照。它还可以包含一个消息字符串，提供有关错误的更多信息。它还可以抑制其他可投掷物品的传播。

如果用户想要创建自己的自定义可投掷类，那么他/她可以扩展可投掷类。

**示例:**

类 MyThrowable 扩展了 Throwable{

//在这里，用户可以创建自己的自定义可投掷

}

GFG 班

Public void test()引发了 MyThrowable{

//创建的自定义可投掷对象可以如下使用

抛出新的 MyThrowable()；

}

}

**java.lang.Throwable** 类的类声明如下:

## Java

```
public class Throwable
    extends Object
    implements Serializable
```

[**构造函数**](https://www.geeksforgeeks.org/constructors-in-java/) **:** 任何类都可以有三种类型的构造函数中的任意一种或者全部三种类型的构造函数。它们是默认的、参数化的和非参数化的构造函数。该类主要定义了以下构造函数:

**公共构造函数**

1.  **Throwable ():** It is a nonparametric constructor, which constructs a new throwable with null details.
2.  **Throwable (string message):** It is a parameterized constructor that constructs a new throwable with specific detailed messages.
3.  **Throwable (string message, throwaway reason):** is a parameterized constructor, which constructs a new throwaway with specific details and reasons.
4.  **Throwable (Throwable cause):** It is a parameterized constructor. By using the toString () method to convert the case into a String, a new throwable is constructed. The throwable has a specific reason and a detailed reason message.

**受保护的构造函数**

1.**可抛出(字符串消息、可抛出原因、布尔使能抑制、布尔可写堆栈跟踪)**:它使用指定的详细消息、原因、启用或禁用的抑制以及启用或禁用的可写堆栈跟踪来构造新的可抛出。

参数如下

消息–详细消息。

原因–原因。(允许空值，表示原因不存在或未知。)

启用抑制–是否启用或禁用抑制

writableStackTrace–堆栈跟踪是否应该是可写的。

[**方法:**](https://www.geeksforgeeks.org/methods-in-java/) 除了上面提到的构造函数之外，throwable 类中还有很多预定义的方法可用。它们是:

1. [**添加抑制的(可抛出的异常)**](https://www.geeksforgeeks.org/throwable-addsuppressed-method-in-java-with-examples/) :该方法将指定的异常附加到被抑制的异常，以便传递该异常。

语法:

公共最终无效添加抑制(可抛出异常)

返回:这个方法不返回任何东西。

2.[**【fillistancktrace()】**](https://www.geeksforgeeks.org/throwable-fillinstacktrace-method-in-java/?ref=rp):填充执行栈痕迹。此方法记录当前 Throwable 对象中当前线程的堆栈帧的当前状态信息。

语法:

public Throwable fillistancktrace()

返回:对当前可抛出实例的引用。

3. [**getCause()**](https://www.geeksforgeeks.org/throwable-getcause-method-in-java-with-examples/?ref=rp) :它返回由需要 Throwable 的构造函数之一提供的原因，或者在创建之后用 initCause()方法设置的原因。

语法:

public Throwable getCause()

返回:当前可投掷的原因。如果原因不存在或未知，则返回 null。

4.[**getlocalized message()**](https://www.geeksforgeeks.org/throwable-getlocalizedmessage-method-in-java-with-examples/?ref=rp):此方法创建当前 Throwable 的本地化描述。

语法:

public 字符串 getlocalizedmessage()

返回:当前可抛出的本地化描述

5.**[**getMessage()**](https://www.geeksforgeeks.org/throwable-getmessage-method-in-java-with-examples/?ref=rp):返回当前可投掷的详细消息串。**

**语法:**

**public String getMessage()**

**返回:当前 Throwable 实例的详细消息字符串(也可能返回 null)**

**6. [**getStackTrace()**](https://www.geeksforgeeks.org/throwable-getstacktrace-method-in-java-with-examples/?ref=rp) :这个方法提供了对 printStackTrace()打印的堆栈跟踪信息的编程访问。它返回一个堆栈跟踪元素数组，每个元素代表一个堆栈帧。数组的第零个元素(假设数组的长度为非零)是序列中的最后一个方法调用。它还表示为堆栈的顶部，并且是创建和抛出这个可抛出对象的点。数组的最后一个元素(假设数组的长度为非零)是序列中的第一个方法调用，它代表堆栈的底部。**

**语法:**

**public stack trace element[]getstackle trace()**

**返回:堆栈跟踪元素的数组，表示与当前 Throwable 相关的堆栈跟踪。**

**7. [**getSuppressed()**](https://www.geeksforgeeks.org/throwable-getsuppressed-method-in-java-with-examples/?ref=rp) :返回一个包含所有被抑制的异常的数组，以便传递这个异常。如果没有异常被禁止或禁止，将返回一个空数组。**

**语法:public final Throwable[]getSuppressed()**

**返回:一个数组，包含为传递此异常而被抑制的所有异常。**

**8. [**初始化原因(可投掷原因)**](https://www.geeksforgeeks.org/throwable-initcause-method-in-java-with-examples/?ref=rp) :将当前可投掷的原因初始化为指定值。这个方法最多可以调用一次。它通常在构造函数中调用，或者在创建 throwable 之后立即调用。**

**语法:公共可抛出原因(可抛出原因)**

**参数:**

**可投掷原因-当前可投掷的原因。**

**投掷:**

**1.IllegalArgumentException:如果原因是当前可抛出的，则会引发此异常，因为可抛出的不能是它自己的原因。**

**2.IllegalStateException:如果已经在当前可抛出对象上调用了此方法，则会发生这种情况。**

**返回:对当前可投掷实例的引用。**

**9.[**print stack trace()**](https://www.geeksforgeeks.org/throwable-printstacktrace-method-in-java-with-examples/?ref=rp):打印当前可抛出及其对标准错误流的回溯。**

**语法:public void printStackTrace()**

**返回:此方法不返回任何内容。**

**10.[**print stack trace(print writer s)**](https://www.geeksforgeeks.org/throwable-printstacktrace-method-in-java-with-examples/?ref=rp):将当前可投掷文件及其回溯打印到指定的打印编写器。**

**语法:public void printStackTrace**

**参数:打印编写器-它是用于输出的打印编写器**

**返回:此方法不返回任何内容。**

**11. [**打印堆栈跟踪(打印流)**](https://www.geeksforgeeks.org/throwable-printstacktrace-method-in-java-with-examples/?ref=rp) :打印当前可投掷文件及其到指定打印流的回溯。**

**语法:public void printStackTrace**

**参数:打印流-它是用于输出的打印流**

**返回:此方法不返回任何内容。**

**12.[**setstack trace(stack trace element【】stack trace)**](https://www.geeksforgeeks.org/throwable-setstacktrace-method-in-java-with-examples/?ref=rp):此方法设置将由 getStackTrace()返回并由 printStackTrace()打印的堆栈跟踪元素及相关方法。**

**语法:public void setstackle trace(stack trace element[]stack trace)**

**参数:StackTraceElement-这些是要与当前 Throwable 关联的堆栈跟踪元素。**

**投掷:**

**如果堆栈跟踪为空或者堆栈跟踪的任何元素为空，则为空**

**返回:**

**此方法不返回任何内容。**

**13. [**toString()**](https://www.geeksforgeeks.org/throwable-tostring-method-in-java-with-examples/?ref=rp) :此方法返回当前可投掷的简短描述。**

**语法:公共字符串 toString()**

**返回:当前可抛出的字符串表示形式。**

**下面的程序演示了 **toString()** 可投掷类的方法:**

**T5】JavaT7

```
// Java program to demonstrate
// the toString() Method.

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

            // Print using tostring()
            System.out.println("Exception: "
                               + e.toString());
        }
    }

    // Method which throws Exception
    public static void testException()
        throws Exception
    {

        throw new Exception(
            "New Exception Thrown");
    }
}
```

T8****T10**输出:**T1

T14

下面程序演示 **getMessage()** 方法 java.lang.Throwable 类:

T5】JavaT0T9T11】输出:T1

T14

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/lang/throwable . html/](https://docs.oracle.com/javase/7/docs/api/java/lang/Throwable.html)**