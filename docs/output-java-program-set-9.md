# Java 程序输出|第 9 集

> 原文:[https://www.geeksforgeeks.org/output-java-program-set-9/](https://www.geeksforgeeks.org/output-java-program-set-9/)

**难度等级**:中级

预测以下 Java 程序的输出。

**程序 1:**

```java
class Gfg
{
    // constructor
    Gfg()
    {
        System.out.println("Geeksforgeeks");
    }

    static Gfg a = new Gfg(); //line 8

    public static void main(String args[])
    {
        Gfg b; //line 12
        b = new Gfg();
    }
}
```

输出:

```java
Geeksforgeeks
Geeksforgeeks

```

**说明:**
我们知道一个类加载时会调用静态变量，静态变量只调用一次。现在，第 13 行导致创建一个对象，该对象依次调用构造函数，第二次打印“极客”。
如果第 8 行静态变量没有被使用，对象将被无限递归调用，导致 StackOverFlow 错误。样本运行见[本](https://ide.geeksforgeeks.org/wtntd4)。

**程序 2:**

```java
class Gfg
{
    static int num;
    static String mystr;

    // constructor
    Gfg()
    {
        num = 100;
        mystr = "Constructor";
    }

    // First Static block
    static
    {
        System.out.println("Static Block 1");
        num = 68;
        mystr = "Block1";
    }

    // Second static block
    static
    {
        System.out.println("Static Block 2");
        num = 98;
        mystr = "Block2";
    }

    public static void main(String args[])
    {
        Gfg a = new Gfg();
        System.out.println("Value of num = " + a.num);
        System.out.println("Value of mystr = " + a.mystr);
    }
}
```

输出:

```java
Static Block 1
Static Block 2
Value of num = 100
Value of mystr = Constructor
```

**解释:**
当类被加载到内存中时，静态块被执行。一个类可以有多个静态块，这些静态块按照写入程序的相同顺序执行。
**注**:静态方法可以不使用类的对象来访问类变量。由于在创建新实例时调用构造函数，因此首先调用静态块，然后调用构造函数。如果我们在不使用对象的情况下运行同一个程序，就不会调用构造函数。

**程序 3:**

```java
class superClass
{
    final public int calc(int a, int b)
    {
        return 0;
    }
}
class subClass extends superClass
{
    public int calc(int a, int b)
    {
        return 1;
    }
}
public class Gfg
{
    public static void main(String args[])
    {
        subClass get = new subClass();
        System.out.println("x = " + get.calc(0, 1));
    }
}
```

输出:

```java
Compilation fails. 
```

**解释:**
类 superClass 中的方法 calc()是 final，因此不能被覆盖。

**程序 4:**

```java
public class Gfg
{
    public static void main(String[] args)
    {
        Integer a = 128, b = 128;
        System.out.println(a == b);

        Integer c = 100, d = 100;
        System.out.println(c == d);
    }
}
```

输出:

```java
false
true
```

**说明:**在 Integer 对象的源代码中我们会找到一个方法‘value of’，在这个方法中我们可以看到 Integer 对象的范围位于 IntegerCache.low(-128)到 IntegerCache.high(127)之间。因此，127 以上的数字不会给出预期的输出。英特尔高速缓存的范围可以从英特尔高速缓存类的源代码中观察到。详见[本](https://blogs.oracle.com/darcy/entry/boxing_and_caches_integer_valueof)。

本文由 **[普拉蒂克·阿加瓦尔](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。