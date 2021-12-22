# 在 Java 中具有相同数据成员的父类和子类

> 原文:[https://www . geesforgeks . org/parent-and-child-class-具有相同数据的 java 成员/](https://www.geeksforgeeks.org/parent-and-child-classes-having-same-data-member-in-java/)

父类的引用变量能够保存其对象引用及其子对象引用。
在 Java 中，方法默认是虚拟的(详见[本](https://www.geeksforgeeks.org/g-fact-43/))。
非方法成员呢。例如，预测以下 Java 程序的输出。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A Java program to demonstrate that non-method
// members are accessed according to reference
// type (Unlike methods which are accessed according
// to the referred object)

class Parent
{
    int value = 1000;
    Parent()
    {
        System.out.println("Parent Constructor");
    }
}

class Child extends Parent
{
    int value = 10;
    Child()
    {
        System.out.println("Child Constructor");
    }
}

// Driver class
class Test
{
    public static void main(String[] args)
    {
        Child obj=new Child();
        System.out.println("Reference of Child Type :"
                           + obj.value);

        // Note that doing "Parent par = new Child()"
        // would produce same result
        Parent par = obj;

        // Par holding obj will access the value
        // variable of parent class
        System.out.println("Reference of Parent Type : "
                           + par.value);
    }
}
```

输出:

```java
Parent Constructor
Child Constructor
Reference of Child Type : 10
Reference of Parent Type : 1000
```

如果父引用变量持有子类的引用，并且我们在父类和子类中都有“值”变量，那么它将引用父类“值”变量，无论它是否持有子类对象引用。持有子类对象引用的引用将不能访问子类的成员(函数或变量)。这是因为父引用变量只能访问父类中的字段。因此，引用变量的类型决定了将调用“值”的哪个版本，而不是被实例化的对象的类型。这是因为编译器只对方法使用特殊的运行时多态机制。(在那里，被实例化的对象的类型决定了要调用的方法的版本)。
可以使用带类型转换的父指针访问子数据成员。完整代码见本最后一个例子[。
本文由**钿泰亚吉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用](https://www.geeksforgeeks.org/java-instanceof-and-its-applications/)[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。