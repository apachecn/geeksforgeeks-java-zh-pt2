# 静态方法与 Java 中的实例方法

> 原文:[https://www . geesforgeks . org/static-methods-vs-instance-methods-Java/](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/)

**实例方法**

实例方法是需要在调用之前创建其类的对象的方法。要调用实例方法，我们必须创建一个在其中定义它的类的对象。

```
public void geek(String name)
{
 // code to be executed....
}
// Return type can be int, float String or user defined data type.
```

**内存分配:**这些方法本身存储在堆的永久生成空间中，但参数(传递给它们的参数)及其局部变量和要返回的值是在堆栈中分配的。它们可以在它们所在的同一个类中调用，也可以从同一个包或其他包中定义的不同类中调用，这取决于提供给所需实例方法的**访问类型**。
**要点:**

*   实例方法属于类的对象，而不属于类，即它们可以在创建类的对象后被调用。
*   实例方法不是基于每个实例存储的，即使使用虚拟方法也是如此。它们存储在一个单独的内存位置，它们只“知道”它们属于哪个对象，因为当您调用它们时，这个指针会被传递。
*   它们可以被覆盖，因为它们是在运行时使用**动态绑定**解析的。

下面是访问实例方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Example to illustrate accessing the instance method .
import java.io.*;

class Foo {

    String name = "";

    // Instance method to be called within the
    // same class or from a another class defined
    // in the same package or in different package.
    public void geek(String name) { this.name = name; }
}

class GFG {
    public static void main(String[] args)
    {

        // create an instance of the class.
        Foo ob = new Foo();

        // calling an instance method in the class 'Foo'.
        ob.geek("GeeksforGeeks");
        System.out.println(ob.name);
    }
}
```

**Output**

```
GeeksforGeeks
```

**静法**

静态方法是 Java 中不需要创建类对象就可以调用的方法。它们由**类名本身**或该类的对象引用来引用。

```
public static void geek(String name)
{
 // code to be executed....
}

// Must have static modifier in their declaration.
// Return type can be int, float, String or user defined data type.
```

**内存分配:**

它们存储在堆的永久生成空间中，因为它们与它们所在的类相关联，而不是与该类的对象相关联。但是它们的局部变量和传递给它们的参数存储在堆栈中。因为它们属于类，所以可以在不创建类的对象的情况下调用它们。

**要点:**

*   静态方法与它们所在的类相关联，即它们在没有创建类实例的情况下被调用，即**类名.方法名(参数)**。
*   它们的设计目标是在从同一类创建的所有对象之间共享。
*   静态方法不能被覆盖，因为它们是由编译器在编译时使用**静态绑定**解析的。但是，我们可以在**超类**和**子类**中有相同名称的方法声明**静态**，但它将被称为 [**方法隐藏**](https://www.geeksforgeeks.org/overriding-in-java/) ，因为派生类方法将隐藏基类方法。

下面是访问静态方法的图示:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Example to illustrate Accessing
// the Static method(s) of the class.
import java.io.*;

class Geek {

    public static String geekName = "";

    public static void geek(String name)
    {
        geekName = name;
    }
}

class GFG {
    public static void main(String[] args)
    {

        // Accessing the static method geek()
        // and field by class name itself.
        Geek.geek("vaibhav");
        System.out.println(Geek.geekName);

        // Accessing the static method geek()
        // by using Object's reference.
        Geek obj = new Geek();
        obj.geek("mohit");
        System.out.println(obj.geekName);
    }
}
```

**Output**

```
vaibhav
mohit
```

**注意:**类中定义的静态变量及其值(原语或引用)存储在 **PermGen** 内存空间中。

**如果静态变量引用一个对象怎么办？**

```
static int i = 1;
static Object obj = new Object();
```

在第一行中，值 1 将存储在 PermGen 部分。在第二行，引用对象将存储在 PermGen 部分，它引用的对象将存储在堆部分。

**何时使用静态方法？**

*   当您拥有可以在同一个类的所有实例之间共享的代码时，将这部分代码放入静态方法中。
*   它们基本上用于访问类的静态字段。

**实例法对比静态法**

*   实例方法可以直接访问实例方法和实例变量。
*   实例方法可以直接访问静态变量和静态方法。
*   静态方法可以直接访问静态变量和静态方法。
*   静态方法不能直接访问实例方法和实例变量。它们必须使用对对象的引用。静态方法不能使用[这个](https://www.geeksforgeeks.org/this-reference-in-java/)关键字，因为没有“this”的实例可以引用。

**参考文献**

*   [https://docs . Oracle . com/javae/tutorial/Java/javaoo/class vars . html](https://docs.oracle.com/javase/tutorial/java/javaOO/classvars.html)
*   叠置溢出

本文由 **Nitsdheerendra** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。