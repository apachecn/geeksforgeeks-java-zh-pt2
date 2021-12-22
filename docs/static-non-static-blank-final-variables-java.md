# Java 中静态和非静态空白最终变量

> 原文:[https://www . geesforgeks . org/static-non-static-blank-final-variables-Java/](https://www.geeksforgeeks.org/static-non-static-blank-final-variables-java/)

变量为我们提供了命名存储，我们的程序可以对其进行操作。类中有两种类型的数据变量:
**实例变量:**实例变量在类中声明，但在方法、构造函数或任何块之外。为堆中的对象分配空间时，会为每个实例变量值创建一个槽。实例变量是在使用关键字“new”创建对象时创建的，并在对象被销毁时被销毁。它们是对象的属性，因此只能使用对象来访问。

**静态变量:**类变量也称为静态变量，在类中用 Static 关键字声明，但在方法、构造函数或块之外。每个类只有一个类变量的副本，不管有多少对象是从它创建的。它们是类的属性，而不是对象的属性，因此可以直接使用类名和对象来使用它们。

```
// Java code to illustrate use of instance and static variables
public class Emp {
    String name;
    int salary;
    static String company;
    public void printDetails()
    {
        System.out.println("Name: " + name);
        System.out.println("Company: " + company);
        System.out.println("Salary: " + salary);
    }
    public static void main(String s[])
    {
        Emp.company = "GeeksForGeeks";
        Emp g = new Emp();
        g.name = "Shubham";
        g.salary = 100000;

        Emp sp = new Emp();
        sp.name = "Chirag";
        sp.salary = 200000;

        g.printDetails();
        sp.printDetails();

        g.company = "Google";
        g.salary = 200000;
        System.out.println("\nAfter change\n");
        g.printDetails();
        sp.printDetails();
    }
}
```

输出:

```
Name: Shubham
Company: GeeksForGeeks
Salary: 100000
Name: Chirag
Company: GeeksForGeeks
Salary: 200000

After change

Name: Shubham
Company: Google
Salary: 200000
Name: Chirag
Company: Google
Salary: 200000

```

在上面的示例中，通过更改公司名称，它反映在所有其他对象中，因为它是一个静态变量。但是改变 g 的工资不会改变 s 的工资，因为工资是一个实例变量。

**空白最终变量:**声明但未赋值的[最终变量](https://www.geeksforgeeks.org/g-fact-48/)称为空白最终变量。它只能在构造函数中初始化。如果它没有被初始化，就会引发编译错误，因为它应该在程序的某个地方被赋予一个值，而这个值也只能从构造函数中被赋予。

**静态空白最终变量:**是声明为静态的空白最终变量。也就是说，声明但未给定值或未初始化的最终静态变量称为静态空白最终变量。它只能通过静态块初始化。
这里有一个例子说明了空白最终变量的初始化-

```
// Java program to illustrate initialization 
// of blank final variables
public class GFG {
    private static final int a;
    private final int b;
    static
    {
        a = 1;
    }
    GFG(int c)
    {
        b = c;
    }
    public static void main(String s[])
    {
        GFG g1 = new GFG(10);
        GFG g2 = new GFG(20);
        System.out.println(GFG.a);
        System.out.println(g1.b);
        System.out.println(g1.b);
    }
}
```

输出:

```
1
10
10

```

在上例中，b 使用构造函数初始化，而 a 使用静态块初始化。

**预测以下程序的输出:**

```
// Java program to illustrate 
// static blank final variable
public class UserLogin {
    public static final long GUEST_ID = -1;
    private static final long USER_ID;
    static
    {
        try {
            USER_ID = getID();
        }
        catch (IdNotFound e) {
            USER_ID = GUEST_ID;
            System.out.println("Logging in as guest");
        }
    }
    private static long getID()
        throws IdNotFound
    {
        throw new IdNotFound();
    }
    public static void main(String[] args)
    {
        System.out.println("User ID: " + USER_ID);
    }
}
class IdNotFound extends Exception {
    IdNotFound() {}
}
```

输出:

```
prog.java:8: error: variable USER_ID might already have been assigned
USER_ID = GUEST_ID;
^
1 error

```

用户标识字段是一个静态的空白结尾。很明显，只有当分配给用户标识失败时，才会在 try 块中引发异常，因此在 catch 块中分配给用户标识是完全安全的。静态初始值设定项块的任何执行都将导致对用户标识的一次赋值，这正是空白期末考试所需要的。但是这个程序失败了，因为，**一个空白的最终字段只能在程序中明确未赋值的点上赋值。**

这里，编译器不确定它是否在 try 块中被赋值，所以程序不编译。我们可以通过移除静态块并在声明时初始化 USER_ID 来解决这个问题。

```
// Java program to illustrate 
// static blank final variable
public class UserLogin {
    public static final long GUEST_ID = -1;
    private static final long USER_ID = getUserIdOrGuest();
    private static long getUserIdOrGuest()
    {
        try {
            return getID();
        }
        catch (IdNotFound e) {
            System.out.println("Logging in as guest");
            return GUEST_ID;
        }
    }
    private static long getID()
        throws IdNotFound
    {
        throw new IdNotFound();
    }
    public static void main(String[] args)
    {
        System.out.println("User ID: " + USER_ID);
    }
}
class IdNotFound extends Exception {
    IdNotFound() {}
}
```

输出:

```
Logging in as guest
User ID: -1

```

本文由 [**舒巴姆·朱尼加**](https://auth.geeksforgeeks.org/profile.php?user=shubhamjuneja11) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。