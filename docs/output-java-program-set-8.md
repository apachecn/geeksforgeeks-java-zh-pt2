# Java 程序输出|第 8 集

> 原文:[https://www.geeksforgeeks.org/output-java-program-set-8/](https://www.geeksforgeeks.org/output-java-program-set-8/)

**难度等级**:中级
预测以下 Java 程序的输出。
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
    public static void main(String args[])
    {
        String s1 = new String("geeksforgeeks");
        String s2 = new String("geeksforgeeks");
        if (s1 == s2)
            System.out.println("Equal");
        else
            System.out.println("Not equal");
    }
}
```

输出:

```
Not equal
```

**解释:**由于，s1 和 s2 是两个不同的对象，所以引用不一样，并且==运算符比较对象引用。因此，它打印“不相等”，以比较字符串中的实际字符。必须使用 equals()方法。

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Person
{
    private void who()
    {
        System.out.println("Inside private method Person(who)");
    }

    public static void whoAmI()
    {
        System.out.println("Inside static method, Person(whoAmI)");
    }

    public void whoAreYou()
    {
        who();
        System.out.println("Inside virtual method, Person(whoAreYou)");
    }
}

class Kid extends Person
{
    private void who()
    {
        System.out.println("Kid(who)");
    }

    public static void whoAmI()
    {
        System.out.println("Kid(whoAmI)");
    }

    public void whoAreYou()
    {
        who();
        System.out.println("Kid(whoAreYou)");
    }
}
public class Gfg
{
    public static void main(String args[])
    {
        Person p = new Kid(); 
        p.whoAmI();
        p.whoAreYou();
    }
}
```

输出:

```
Inside static method, Person(whoAmI)
Kid(who)
Kid(whoAreYou)
```

**解释:**静态方法发生静态绑定(或编译时)。这里 *p.whoAmI()* 调用静态方法，因此它在编译时被调用，从而导致静态绑定，并在 Person 类中打印该方法。
而*p . whoiyou()*调用 *Kid* 类中的方法，因为默认情况下，Java 将其作为虚拟方法，即动态绑定。

**程序三:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
    public static void main(String args[])
    {
        try
        {
            System.out.println("First statement of try block");
            int num=45/3;
            System.out.println(num);
        }
        catch(Exception e)
        {
            System.out.println("Gfg caught Exception");
        }
        finally
        {
            System.out.println("finally block");
        }
        System.out.println("Main method");
    }
}
```

输出:

```
First statement of try block
15
finally block
Main method
```

**解释:**
由于没有异常，所以不调用 catch 块，但是无论异常是否被处理，*最后*块总是在 try 块之后执行。

**程序 4:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class One implements Runnable
{
    public void run()
    {
        System.out.print(Thread.currentThread().getName());
    }
}
class Two implements Runnable
{
    public void run()
    {
        new One().run();
        new Thread(new One(),"gfg2").run();
        new Thread(new One(),"gfg3").start();
    }
}
class Three
{
    public static void main (String[] args)
    {
        new Thread(new Two(),"gfg1").start();
    }
}
```

输出:

```
gfg1gfg1gfg3
```

**解释:**最初新线程以名称 *gfg1* 开始，然后在第二类中，第一个运行方法运行名为 *gfg1* 的线程，然后在此之后通过调用运行方法创建一个新线程，但是由于只能通过调用 start 方法创建一个新线程，因此前一个线程执行该操作，并且再次打印 *gfg1* 。现在通过调用 start 方法创建了一个新线程，因此一个新线程以 *gfg3* 名称开始，并因此打印 *gfg3* 。
本文由[**Pratik Agarwal**](https://www.facebook.com/Pratik.Agarwal01)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。