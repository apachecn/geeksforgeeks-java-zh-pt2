# Java 程序的输出|第 14 集(构造函数)

> 原文:[https://www . geesforgeks . org/output-Java-programs-set-14-构造函数/](https://www.geeksforgeeks.org/output-java-programs-set-14-constructors/)

先决条件–[Java 构造函数](https://www.geeksforgeeks.org/constructors-in-java/)

**1)以下程序的输出是什么？**

```java
class Helper
{
    private int data;
    private Helper()
    {
        data = 5;
    }
}
public class Test
{
    public static void main(String[] args)
    {
        Helper help = new Helper();
        System.out.println(help.data);
    }
}
```

a)编译错误
b) 5
c)运行时错误
d)这些都没有

**Ans。** (a)
**解释:** A [私有构造函数](https://www.geeksforgeeks.org/private-constructors-and-singleton-classes-in-java/)不能用于初始化定义它的类之外的对象，因为它对外部类不再可见。

**2)以下程序的输出是什么？**

```java
public class Test implements Runnable
{
    public void run()
    {
        System.out.printf(" Thread's running ");
    }

    try
    {
        public Test()
        {
            Thread.sleep(5000);
        }   
    } 
    catch (InterruptedException e) 
    {
        e.printStackTrace();
    }

    public static void main(String[] args)
    {
        Test obj = new Test();
        Thread thread = new Thread(obj);
        thread.start();
        System.out.printf(" GFG ");
    }
}
```

a) GFG 线程运行
b)线程运行 GFG
c)编译错误
d)运行时间错误

**Ans。** (c)
**解释:**构造函数不能包含在 try/catch 块中。

**3)以下程序的输出是什么？**

```java
class Temp
{
    private Temp(int data)
    {
        System.out.printf(" Constructor called ");
    }
    protected static Temp create(int data)
    {
        Temp obj = new Temp(data);
        return obj;
    }
    public void myMethod()
    {
        System.out.printf(" Method called ");
    }
}

public class Test
{
    public static void main(String[] args)
    {
        Temp obj = Temp.create(20);
        obj.myMethod();
    }
}
```

a)构造函数调用方法调用
b)编译错误
c)运行时错误
d)以上都不是

**Ans。** (a)
**解释:**当构造函数被标记为私有时，从某个外部类创建该类的新对象的唯一方法是使用创建新对象的方法，如上面在程序中定义的那样。create()方法负责从其他外部类创建 Temp 对象。一旦创建了对象，就可以从创建对象的类中调用它的方法。
 **4)以下程序的输出是什么？**

```java
public class Test
{
    public Test()
    {
        System.out.printf("1");
        new Test(10);
        System.out.printf("5");
    }
    public Test(int temp)
    {
        System.out.printf("2");
        new Test(10, 20);
        System.out.printf("4");
    }
    public Test(int data, int temp)
    {
        System.out.printf("3");

    }

    public static void main(String[] args)
    {
        Test obj = new Test();

    }

}
```

a) 12345
b)编译错误
c) 15
d)运行时错误

**Ans。**(一)
**说明:** [构造函数可以被](https://www.geeksforgeeks.org/constructor-chaining-java-examples/)连锁，重载。当调用 Test()时，它会创建另一个调用构造函数 Test(int temp)的测试对象。

**5)以下程序的输出是什么？**

```java
class Base
{
    public static String s = " Super Class ";
    public Base()
    {
        System.out.printf("1");
    }
}
public class Derived extends Base
{
    public Derived()
    {
        System.out.printf("2");
        super();
    }

    public static void main(String[] args)
    {
        Derived obj = new Derived();
        System.out.printf(s);
    }
}
```

a) 21 超类
b)超类 21
c)编译错误
d) 12 超类
T4】Ans。 (c)
**解释:**构造函数对超类的调用必须是派生类的构造函数中的第一条语句。
私人
本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。