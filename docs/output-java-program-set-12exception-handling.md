# Java 程序输出|第 12 集(异常处理)

> 原文:[https://www . geesforgeks . org/output-Java-program-set-12 异常处理/](https://www.geeksforgeeks.org/output-java-program-set-12exception-handling/)

**先决条件:** [异常处理](https://www.geeksforgeeks.org/java/#Exception Handling)、[试捕中的控制流-最后](https://www.geeksforgeeks.org/flow-control-in-try-catch-finally-in-java/)
**1)以下程序的输出是什么？**

```java
public class Test
{
    public static void main(String[] args)
    {
        try
        {
            System.out.printf("1");
            int sum = 9 / 0;
            System.out.printf("2");
        }
        catch(ArithmeticException e)
        {
            System.out.printf("3");
        }
        catch(Exception e)
        {
            System.out.printf("4");
        }
        finally
        {
            System.out.printf("5");
        }
    }
}
```

a)1325
b)1345
c)1342
d)135

**Ans。** (d)
**解释:**一旦 try block 出现异常，执行传递到对应的**catch 语句，不返回 try block。一次只执行一个 catch 块。无论异常是否发生，总是执行 finally block。
 **2)以下程序的输出是什么？****

```java
public class Test
{
    private void m1()
    {
        m2();
        System.out.printf("1");
    }
    private void m2()
    {
        m3();
        System.out.printf("2");
    }
    private void m3()
    {
        System.out.printf("3");
        try
        {
            int sum = 4/0;
            System.out.printf("4");
        }
        catch(ArithmeticException e)
        {
            System.out.printf("5");
        }

        System.out.printf("7");
    }
    public static void main(String[] args)
    {
        Test obj = new Test();
        obj.m1();
    }
}
```

**a)35721
b)354721
c)3521
d)35
T4【Ans。 (a)
**解释:**如果在 catch 语句中处理了异常，则程序在执行了与该异常对应的 catch 语句之后，继续其正常执行。此外，当 try 块中出现异常时，try 块中的其余程序不会执行。**

****3)以下程序的输出是什么？****

```java
public class Test
{
    public static void main(String[] args)
    {
        try
        {
            System.out.printf("1");
            int data = 5 / 0;
        }
        catch(ArithmeticException e)
        {
            System.out.printf("2");
            System.exit(0);
        }
        finally
        {
            System.out.printf("3");
        }
        System.out.printf("4");
    }
}
```

**a)12
b)1234
c)124
d)123**

****Ans。** (a)
**解释:**最终块内部的代码不执行的唯一情况是在程序中显式调用 System.exit(0)时。然后调用 exit 语句，程序终止，不再执行。
 **4)以下程序的输出是什么？****

```java
public class Test
{
    public static void main(String[] args)
    {
        try
        {
            System.out.printf("1");
            int data = 5 / 0;
        }
        catch(ArithmeticException e)
        {
            Throwable obj = new Throwable("Sample");
            try 
            {
                throw obj;
            } 
            catch (Throwable e1) 
            {
                System.out.printf("8");
            }
        }
        finally
        {
            System.out.printf("3");
        }
        System.out.printf("4");
    }
}
```

**a)编译错误
b)运行时错误
c) 1834
d) 134**

****Ans。** (c)
**解释:**例外可以抛出 catch 子句。这样做是为了在运行时更改异常类型。catch 子句中的异常是通过创建类 Throwable 的实例引发的，如程序所示。**

****5)以下程序的输出是什么？****

```java
import java.io.EOFException;
import java.io.IOException;

public class Test
{
    public static void main(String[] args)
    {
        try
        {
            System.out.printf("1");
            int value = 10 / 0;
            throw new IOException();
        }
        catch(EOFException e)
        {
            System.out.printf("2");
        }
        catch(ArithmeticException e)
        {
            System.out.printf("3");
        }
        catch(NullPointerException e)
        {
            System.out.printf("4");
        }
        catch(IOException e)
        {
            System.out.printf("5");
        }
        catch(Exception e)
        {
            System.out.printf("6");
        }
    }
}
```

**a)1346
b)136726
c)136
d)13
T4【Ans。 (d)
**解释:**在多 catch 语句中，必须从更具体到更一般地列出例外。只执行一个对发生的异常最特定的 catch 语句。**

**本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**