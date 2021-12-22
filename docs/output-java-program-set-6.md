# Java 程序输出|第 6 集

> 原文:[https://www.geeksforgeeks.org/output-java-program-set-6/](https://www.geeksforgeeks.org/output-java-program-set-6/)

**难度等级:**中级

预测以下 Java 程序的输出。

**程序 1:**

```
class First
{
    public First() {  System.out.println("a"); }
}

class Second extends First
{
    public Second()  {  System.out.println("b"); }
}

class Third extends Second
{
    public Third()   {  System.out.println("c"); }
}

public class MainClass
{
    public static void main(String[] args)
    {
        Third c = new Third();
    }
}
```

输出:

```
a
b
c

```

**说明:**
在新建一个‘Third’类型的对象时，在调用 Third 类的默认构造函数之前，先调用 super 类的默认构造函数即 Second 类，然后在 super 类的默认构造函数之前，再调用 First 类的默认构造函数。并因此给出这样的输出。

**程序 2:**

```
class First
{
    int i = 10;

    public First(int j)
    {
        System.out.println(i); 
        this.i = j * 10;
    }
}

class Second extends First
{
    public Second(int j)
    {
        super(j); 
        System.out.println(i); 
        this.i = j * 20;
    }
}

public class MainClass
{
    public static void main(String[] args)
    {
        Second n = new Second(20); 
        System.out.println(n.i);
    }
}
```

输出:

```
10
200
400

```

**解释:**
由于在‘Second’类中它没有自己的‘I’，所以这个变量是从超类继承而来的。另外，当我们创建第二个对象时，会调用父对象的构造函数。

**程序 3:**

```
import java.util.*; 
class I 
{
    public static void main (String[] args) 
    {
        Object i = new ArrayList().iterator(); 
        System.out.print((i instanceof List) + ", "); 
        System.out.print((i instanceof Iterator) + ", "); 
        System.out.print(i instanceof ListIterator); 
    } 
}
```

输出:

```
false, true, false

```

**解释:**
iterator()方法以适当的顺序返回列表中元素的迭代器，它不返回 list 或 ListIterator 对象。可以通过调用列表迭代器方法获得列表迭代器。

**程序 4:**

```
class ThreadEx extends Thread
{
    public void run()
    {
        System.out.print("Hello...");
    }
    public static void main(String args[])
    {
        ThreadEx T1 = new ThreadEx();
        T1.start();
        T1.stop();
        T1.start();
    }
}
```

输出:

```
Run Time Exception

```

**说明:**
线程“主”Java . lang . illegalthreadstateexception at Java . lang . Thread . start
线程不能启动两次。

本文由 **Pratik Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。