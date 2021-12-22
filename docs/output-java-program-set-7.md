# Java 程序输出|第 7 集

> 原文:[https://www.geeksforgeeks.org/output-java-program-set-7/](https://www.geeksforgeeks.org/output-java-program-set-7/)

**难度等级:**中级

预测以下 Java 程序的输出。

**程序 1 :**

```
public class Calculator
{
    int num = 100;
    public void calc(int num)  { this.num = num * 10;  }
    public void printNum()     { System.out.println(num); }

    public static void main(String[] args)
    {
        Calculator obj = new Calculator();
        obj.calc(2);
        obj.printNum();
    }
}
```

**选项:**
A)20
B)100
C)1000
D)2
**答案:A) 20**
**说明:**这里类实例变量名(num)与 *calc()* 方法局部变量名(num)相同。所以引用 *calc()* 方法中的类实例变量时，使用 **[这个](https://www.geeksforgeeks.org/this-reference-in-java/)** 关键字。所以在语句**中，this.num = num * 10** ， *num* 代表值为 2 的方法的局部变量， *this.num* 代表初始值为 100 的类实例变量。现在在 *printNum()* 方法中，由于它没有与类实例变量同名的局部变量，所以我们可以直接使用 *num* 引用实例变量，虽然 *this.num* 可以使用。

**程序 2 :**

```
public class MyStuff
{
    String name;

    MyStuff(String n) {  name = n;  }

    public static void main(String[] args)
    {
        MyStuff m1 = new MyStuff("guitar");
        MyStuff m2 = new MyStuff("tv");
        System.out.println(m2.equals(m1));
    }

    @Override
    public boolean equals(Object obj)
    {
        MyStuff m = (MyStuff) obj;
        if (m.name != null)  { return true;  }
        return false;
    }
}
```

**选项:**
A)输出为真，MyStuff 实现 Object.equals()契约。
B)输出为假，MyStuff 完成 Object.equals()契约。
C)输出为真，MyStuff 未履行 Object.equals()合同。
D)输出为假，MyStuff 未履行 Object.equals()合同。

**回答:** C)输出为真，MyStuff 未履行 Object.equals()合同。
**解释:**由于*在 Object 类中等于(Object obj)* 方法，在等价关系的基础上比较两个对象。但是这里我们只是确认对象是否为空，所以它不满足 [Object.equals()](https://www.geeksforgeeks.org/overriding-equals-method-in-java/) 契约。由于 *m1* 不为空，将打印 true。

**程序 3 :**

```
class Alpha
{
    public String type = "a ";
    public Alpha() {  System.out.print("alpha "); }
}

public class Beta extends Alpha
{
    public Beta()  {  System.out.print("beta ");  }

    void go()
    {
        type = "b ";
        System.out.print(this.type + super.type);
    }

    public static void main(String[] args)
    {
        new Beta().go();
    }
}
```

**选项:**
a)αβb
b)αβa b
c)βαb
d)βαa b

**回答:**A)αβb
T3】解释: The statement **new Beta()。go()** 分两个阶段执行。在第一阶段 *Beta* 类构造函数被调用。 *Beta* 类中没有实例成员。所以现在执行 *Beta* 类构造函数。由于 *Beta* 类扩展了 *Alpha* 类，所以调用转到 *Alpha* 类构造函数，因为默认情况下(编译器放入的)第一条语句是 *Beta* 类构造函数中的 **super()** 。现在作为一个实例变量(*类型*)存在于 *Alpha* 类中，所以它将获得内存，现在 *Alpha* 类构造函数被执行，那么调用返回到 *Beta* 类构造函数下一条语句。于是*阿尔法贝塔*就打印出来了。
第二阶段 *go()* 方法在此对象上调用。因为对象中只有一个变量(*类型*，其值为 *a* 。所以会改成 *b* 打印两次。这里的[超级关键词](https://www.geeksforgeeks.org/super-keyword/)是没有用的。

**程序 4 :**

```
public class Test
{
    public static void main(String[] args)
    {
        StringBuilder s1 = new StringBuilder("Java");
        String s2 = "Love";
        s1.append(s2);
        s1.substring(4);
        int foundAt = s1.indexOf(s2);
        System.out.println(foundAt);
    }
}
```

**选项:**
A)-1
B)3
C)4
D)A**StringIndexOutOfBoundsException**在运行时抛出。
**答案:** C) 4
**解释:** *追加(String str)* 方法，将 str 连接到 *s1* 。*子串(int index)* 方法返回从给定索引到结尾的字符串。但是由于没有任何字符串变量来存储返回的字符串，所以它将被销毁。现在 *indexOf(字符串 s2)* 方法返回第一次出现的 *s2* 的索引。所以 4 被打印为 S1 =“JavaLove”。

**程序 5 :**

```
class Writer
{
    public  static void write()
    {
        System.out.println("Writing...");
    }
}
class Author extends Writer
{
    public  static void write()
    {
        System.out.println("Writing book");
    }
}

public class Programmer extends Author
{
    public  static void write()
    {
        System.out.println("Writing code");
    }

    public static void main(String[] args)
    {
        Author a = new Programmer();
        a.write();
    }
}
```

**选项:**
A)写…
B)写书
C)写代码
D)编译失败

**回答:** B)写书
**说明:**既然静态方法不能被覆盖，那么创建哪个类对象就无所谓了。由于 *a* 是*作者*引用类型，所以总是调用*作者*类方法。如果我们从*作者*类中移除 *write()* 方法，那么就调用 *Writer* 类方法，因为*作者*类扩展了 *Writer* 类。

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。