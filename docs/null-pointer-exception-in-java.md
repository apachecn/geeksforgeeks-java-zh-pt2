# Java 中的空指针异常

> 原文:[https://www . geesforgeks . org/null-pointer-exception-in-Java/](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)

**NullPointerException** 是一个 RuntimeException。在 [Java](https://www.geeksforgeeks.org/java/) 中，可以为对象引用分配一个特殊的空值。当程序试图使用具有空值的对象引用时，会引发 NullPointerException。

这些可以是:

*   从空对象调用方法。
*   访问或修改空对象的字段。
*   取 null 的长度，就像它是一个数组一样。
*   访问或修改空对象的槽，就像它是一个数组一样。
*   抛出 null，就好像它是一个可抛出的值。
*   当您尝试在空对象上同步时。

**为什么我们需要空值？**
Null 是 Java 中使用的特殊值。主要用于表示没有给引用变量赋值。null 的一个应用是实现像链表和树这样的数据结构。其他应用包括空对象模式(详见[本](http://www.oodesign.com/null-object-pattern.html))和[单例模式](https://www.geeksforgeeks.org/singleton-design-pattern/)。Singleton 模式确保只创建一个类的实例，并且旨在提供对对象的全局访问点。

最多创建一个类实例的一个示例方法是将它的所有构造函数声明为私有，然后创建一个返回该类唯一实例的公共方法:

```
// To use randomUUID function.
import java.util.UUID;
import java.io.*;

class Singleton
{
    // Initializing values of single and ID to null.
    private static Singleton single = null;
    private String ID = null;

    private Singleton()
    {
        /* Make it private, in order to prevent the 
           creation of new instances of the Singleton
           class. */

        // Create a random ID
        ID = UUID.randomUUID().toString();
    }

    public static Singleton getInstance()
    {
        if (single == null)
            single = new Singleton();
        return single;
    }

    public String getID()
    {
        return this.ID;
    }
}

// Driver Code
public class TestSingleton
{
    public static void main(String[] args)
    {
        Singleton s = Singleton.getInstance();
        System.out.println(s.getID());
    }
}
```

输出:

```
10099197-8c2d-4638-9371-e88c820a9af2

```

在上面的例子中，单例类的静态实例。该实例在 Singleton getInstance 方法中最多初始化一次。

**如何避免 NullPointerException？**
为了避免 NullPointerException，我们必须确保所有的对象都被正确初始化，然后才能使用它们。当我们声明一个引用变量时，在我们向对象请求一个方法或字段之前，我们必须验证该对象不是空的。

以下是解决该问题的常见问题。

**情况 1:字符串与文字的比较**

一个非常常见的案例问题涉及字符串变量和文字之间的比较。文字可以是字符串或枚举的元素。与其从 null 对象调用方法，不如考虑从文本调用它。

```
// A Java program to demonstrate that invoking a method
// on null causes NullPointerException
import java.io.*;

class GFG
{
    public static void main (String[] args)
    {
        // Initializing String variable with null value
        String ptr = null;

        // Checking if ptr.equals null or works fine.
        try
        {
            // This line of code throws NullPointerException
            // because ptr is null
            if (ptr.equals("gfg"))
                System.out.print("Same");
            else 
                System.out.print("Not Same");
        }
        catch(NullPointerException e)
        {
            System.out.print("NullPointerException Caught");
        }
    }
}
```

输出:

```
NullPointerException Caught

```

我们可以通过对文字而不是对象调用 equals 来避免 NullPointerException。

```
// A Java program to demonstrate that we can avoid
// NullPointerException
import java.io.*;

class GFG
{
    public static void main (String[] args)
    {
        // Initialing String variable with null value
        String ptr = null;

        // Checking if ptr is null using try catch.
        try
        {
            if ("gfg".equals(ptr))
                System.out.print("Same");
            else 
                System.out.print("Not Same");            
        }
        catch(NullPointerException e)
        {
            System.out.print("Caught NullPointerException");
        }
    }
}
```

输出:

```
Not Same
```

**案例 2:检查方法的参数**

在执行新方法的主体之前，我们应该首先检查它的参数是否为空值，只有在正确检查了参数之后，才继续执行该方法。否则，它将抛出一个 **IllegalArgumentException** ，并通知调用方法传递的参数有问题。

```
// A Java program to demonstrate that we should
// check if parameters are null or not before
// using them.
import java.io.*;

class GFG
{
    public static void main (String[] args)
    {
        // String s set an empty string  and calling getLength()
        String s = "";
        try
        {
            System.out.println(getLength(s));
        }
        catch(IllegalArgumentException e)
        {
            System.out.println("IllegalArgumentException caught");
        }

        // String s set to a value and calling getLength()
        s = "GeeksforGeeks";
        try
        {
            System.out.println(getLength(s));
        }
        catch(IllegalArgumentException e)
        {
            System.out.println("IllegalArgumentException caught");
        }

        // Setting s as null and calling getLength()
        s = null;
        try
        {
            System.out.println(getLength(s));
        }
        catch(IllegalArgumentException e)
        {
            System.out.println("IllegalArgumentException caught");
        }
    }

    // Function to return length of string s. It throws
    // IllegalArgumentException if s is null.
    public static int getLength(String s)
    {
        if (s == null)
            throw new IllegalArgumentException("The argument cannot be null");
        return s.length();
    }
}
```

输出:

```
0
13
IllegalArgumentException caught

```

**情况 3:使用三元运算符**

三元运算符可用于避免 NullPointerException。首先，评估布尔表达式。如果表达式为**真**，则返回值 1，否则返回值 2。我们可以使用三元运算符来处理空指针:

```
// A Java program to demonstrate that we can use
// ternary operator to avoid NullPointerException.
import java.io.*;

class GFG
{
    public static void main (String[] args)
    {
        // Initializing String variable with null value
        String str = null;
        String message = (str == null) ? "" :
                          str.substring(0,5);
        System.out.println(message);

        // Initializing String variable with null value
        str = "Geeksforgeeks";
        message = (str == null) ? "" : str.substring(0,5);
        System.out.println(message);
    }
}
```

输出:

```
Geeks

```

如果字符串的引用为 **null** ，消息变量将为空，如情况 1 所示。否则，如果 str 指向**实际数据**，消息将检索其前 6 个字符，如情况 2。

相关文章–[关于 Java 中 Null 的有趣事实](https://www.geeksforgeeks.org/interesting-facts-about-null-in-java/)

本文由 **[尼基尔·梅赫尔瓦尔](https://auth.geeksforgeeks.org/profile.php?user=Nikhil%20Meherwal&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。