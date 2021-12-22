# Java 程序输出|第 11 集

> 原文:[https://www.geeksforgeeks.org/output-java-program-set-11/](https://www.geeksforgeeks.org/output-java-program-set-11/)

预测以下 Java 程序的输出:

**问题 1 :**

```java
public class Base
{
    private int data;

    public Base()
    {
        data = 5;
    }

    public int getData()
    {
        return this.data;
    }
}

class Derived extends Base
{
    private int data;
    public Derived()
    {
        data = 6;
    }
    private int getData()
    {
        return data;
    }

    public static void main(String[] args)
    {
        Derived myData = new Derived();
        System.out.println(myData.getData());
    }
}
```

a) 6
b) 5
c)编译时错误
d)运行时错误

回答(c)
**说明:**在覆盖超类的方法时，[子类中的方法声明不能比超类](https://www.geeksforgeeks.org/more-restrictive-access-is-given-to-a-derived-class-method-in-java/)中声明的更严格。

**问题 2 :**

```java
public class Test
{
    private int data = 5;

    public int getData()
    {
        return this.data;
    }
    public int getData(int value)
    {
        return (data+1);
    }
    public int getData(int... value)
    {
        return  (data+2);
    }

    public static void main(String[] args)
    {
        Test temp = new Test();
        System.out.println(temp.getData(7, 8, 12));
    }
}
```

a)编译时或运行时错误
b) 8
c) 10
d) 7

回答(d)
解释: [(int… values)作为参数传递给一个方法，当你不知道输入参数的个数但知道参数的类型](https://www.geeksforgeeks.org/variable-arguments-varargs-in-java/)(在这种情况下是 int)。当在主方法中创建新对象时，变量数据被初始化为 5。对具有属性(7，8，12)的 getData()方法的调用会调用第三个 getData()方法，该方法将数据变量的值增加 2 并返回 7。

**问题 3:**

```java
public class Base
{
    private int multiplier(int data)
    {
        return data*5;
    }
}

class Derived extends Base
{
    private static int data;
    public Derived()
    {
        data = 25;
    }
    public static void main(String[] args)
    {
        Base temp = new Derived();
        System.out.println(temp.multiplier(data));
    }
}
```

a) 125
b) 25
c)运行时错误
d)编译时错误

回答(d)
**解释:**由于法器被标记为私有，所以它不是继承的，因此对派生者不可见。

**问题 4:**
关于最后一个 block，下面哪个是 FALSE？
a)每个试块，最后只能有 1 个试块。
b)如果程序通过调用 System.exit()退出，则不会执行 finally block
c)如果 catch 语句中没有处理异常，在终止程序之前，JVM 执行 finally 块
d) finally 块包含重要的代码段，因此在 java 代码中有/没有 try 块的情况下执行 finally 块内部的代码。

答案(d)
**解释:**语句(d)为假，因为 finally blocks 只有在 try 或 catch block 成功时才能存在。使用 finally 块而不使用 try 块会产生编译时错误。

**问题 5:**

```java
import java.io.IOException;
import java.util.EmptyStackException;

public class newclass
{
    public static void main(String[] args)
    {
        try
        {
            System.out.printf("%d", 1);
            throw(new Exception());
        }
        catch(IOException e)
        {
            System.out.printf("%d", 2);
        }
        catch(EmptyStackException e)
        {
            System.out.printf("%d", 3);
        }
        catch(Exception e)
        {
            System.out.printf("%d", 4);
        }
        finally
        {
            System.out.printf("%d", 5);
        }
    }
}
```

a)12345
b)15
c)135
d)145

回答(d)
**解释:**捕捉语句按顺序写:更具体到更一般。在上面的代码中，抛出了一个异常类型的新异常。首先，代码跳到第一个 catch 块寻找异常处理程序。但是由于 IOException 不是同一类型的
，它会向下移动到第二个捕捉块，最后移动到第三个，在那里
捕捉到异常并打印 4。因此，答案是 145，因为块的执行顺序
是:try- > catch- > finally。

**问题 6:**

```java
public class javaclass
{
    static
    {
        System.out.printf("%d", 1);
    }
    static
    {
        System.out.printf("%d", 2);
    }
    static
    {
        System.out.printf("%d", 3);
    }
    private static int myMethod()
    {
        return 4;
    }
    private int function()
    {
        return 5;
    }

    public static void main(String[] args)
    {
        System.out.printf("%d", (new javaclass()).function() + myMethod());
    }
}
```

a)123
b)45
c)12345
d)1239

回答(d)
**解释:**Java 中的静态块甚至在编译器调用 main 之前就被执行了。在主方法中，创建了一个新的 javaclass 对象，并调用了它的 function()方法，该方法返回 5，静态方法 myMethod()返回 4，即 4+5 = 9。因此，程序的输出是 1239，因为甚至在 main 方法执行之前就在控制台上打印了 123，并且执行时 main 方法返回 9。

本文由 **Mayank** 投稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。