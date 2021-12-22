# Java 中受保护的关键字，带示例

> 原文:[https://www . geesforgeks . org/protected-keyword-in-Java-with-examples/](https://www.geeksforgeeks.org/protected-keyword-in-java-with-examples/)

**Protected** 关键字在 Java 中是指它的一个[访问修饰符](https://www.geeksforgeeks.org/access-modifiers-java/)。可以从以下位置访问声明为受保护的方法或数据成员:

*   在同一个班级里。
*   相同包的子类。
*   同一包的不同类别。
*   不同包的子类。

各种修饰语的访问可以从下表中看出。
[![](img/4b70c70c9c710832ff97a5e16a8fc3e3.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Access-Modifiers-in-Java.png)

**要点:**

1.  如果想要访问包外的受保护修改器，那么需要 **[继承](https://www.geeksforgeeks.org/inheritance-in-java/)**才能应用。
2.  保护[构造函数](https://www.geeksforgeeks.org/constructors-in-java/)可以防止用户在包之外创建类的实例。
3.  在[覆盖](https://www.geeksforgeeks.org/overriding-in-java/)的过程中，当[变量](https://www.geeksforgeeks.org/variables-in-java/)或方法受到保护时，只能使用公共或受保护的修饰符将其覆盖到其他子类。
4.  无法保护外部类和接口。

让我们借助一个例子来理解 protected 关键字:
**例子:**在这个例子中，我们将创建两个包 p1 和 p2。p1 中的 A 类被公开，以便在 p2 中访问它。A 类中的方法显示是受保护的，B 类是从 A 类继承的，然后通过创建 B 类的对象来访问这个受保护的方法

**T1】包 P1T3】**

```
// Java program to illustrate
// protected modifier

package p1;

// Class A
public class A {
    protected void display()
    {
        System.out.println("GeeksforGeeks");
    }
}
```

**T1】包 p2T3】**

```
// Java program to illustrate
// protected modifier

package p2;

// import all classes in package p1
import p1.*;

// Class B is a subclass of A
class B extends A {
    public static void main(String args[])
    {
        B obj = new B();
        obj.display();
    }
}
```

**输出:**

```
GeeksforGeeks
```

现在让我们尝试分析不同的访问条件:

1.  **Calling protected function without extending the parent class:** In this example, we will create two packages p1 and p2\. Class A in p1 is made public, to access it in p2\. The method display in class A is protected. But the code will not be able to access the function “display” since the child class has not inherited its value from the main class and will throw an exception as shown.
    **<u>Package p1</u>**

    ```
    // Java program to illustrate
    // protected modifier

    package p1;

    // Class A
    public class A {
        protected void display()
        {
            System.out.println("GeeksforGeeks");
        }
    }
    ```

    **T1】包 p2T3】**

    ```
    // Java program to illustrate
    // protected modifier

    package p2;

    // import all classes in package p1
    import p1.*;

    // Class B is a subclass of A
    class B {
        public static void main(String args[])
        {
            B obj = new B();
            obj.display();
        }
    }
    ```

    这将引发以下错误:

    ```
    Exception in thread "main" 
    java.lang.RuntimeException: 
    Uncompilable source code - 
    Erroneous sym type: p2.B.display
        at p2.B.main(B.java:16)
    ```

2.  **Accessing a protected class:** In this example we tried to access a protected class A resulting in error.

    ```
    // Java program to illustrate
    // protected modifier

    package p1;

    // Class A
    protected class A {
        void display()
        {
            System.out.println("GeeksforGeeks");
        }
    }
    ```

    **T1】包 p2T3】**

    ```
    // Java program to illustrate
    // protected modifier

    package p2;

    // import all classes in package p1
    import p1.*;

    // Class B is a subclass of A
    class B extends A {
        public static void main(String args[])
        {
            B obj = new B();
            obj.display();
        }
    }
    ```

    这将引发以下错误:

    ```
    Exception in thread "main" 
    java.lang.RuntimeException: 
    Uncompilable source code - 
    Erroneous sym type: p2.B.display
        at p2.B.main(B.java:16)
    ```

3.  **Accessing display function from the same package but different class:** In this example we have accessed to access a protected function “display” from the same package but different class
    **<u>Package p1</u>**

    ```
    // Java program to illustrate
    // protected modifier

    package p1;

    // Class A
    public class A {
        protected void display()
        {
            System.out.println("GeeksforGeeks");
        }
    }
    ```

    **<u>丙类</u>T3】**

    ```
    // Java program to illustrate
    // protected modifier

    // Class C is a subclass of A
    public class C {
        public static void main(String args[])
        {
            A obj = new A();
            obj.display();
        }
    }
    ```

    **输出:**

    ```
    GeeksforGeeks
    ```

4.  **Accessing display function from a different package:** In this example we have tried to access the protected function display from a different package by inheritance and extending the class.
    **<u>Package p1</u>**

    ```
    // Java program to illustrate
    // protected modifier

    package p1;

    // Class A
    public class A {
        protected void display()
        {
            System.out.println("GeeksforGeeks");
        }
    }
    ```

    **T1】包 p2T3】**

    ```
    // Java program to illustrate
    // protected modifier

    package p2;

    // import all classes in package p1
    import p1.*;

    // Class B is a subclass of A
    class B extends A {
        public static void main(String args[])
        {
            B obj = new B();
            obj.display();
        }
    }
    ```

    **输出:**

    ```
    GeeksforGeeks
    ```

5.  **Accessing a protected class by overriding to sub-class within same package:** In this example we have designed two classes A and C, where class C is the overridden one.
    **<u>class A</u>**

    ```
    // Java program to illustrate
    // protected modifier
    package p1;

    // Class A
    public class A {
        protected void display()
        {
            System.out.println("Class A");
        }
    }
    ```

    **<u>丙类</u>T3】**

    ```
    // Java program to illustrate
    // protected modifier

    public class C extends A {

        // overridden function
        protected void display()
        {
            System.out.println("Class C");
        }
        public static void main(String args[])
        {
            C obj1 = new C();
            obj1.display();
        }
    }
    ```

    **输出:**

    ```
    Class C
    ```