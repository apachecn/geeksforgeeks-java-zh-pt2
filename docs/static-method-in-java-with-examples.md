# Java 中的静态方法示例

> 原文:[https://www . geesforgeks . org/static-method-in-Java-with-examples/](https://www.geeksforgeeks.org/static-method-in-java-with-examples/)

static 关键字用于构造无论是否生成类的任何实例都将存在的方法。任何使用 static 关键字的方法都称为静态方法。

**静态方法的特点:**

*   Static methods in Java are part of a class, not an instance of that class.
*   This method can be accessed by every instance of the class.
*   Static methods can access class variables (static variables) without using class objects (instances).
*   Static methods can only access static data. It cannot access non-static data (instance variables).
*   In both static and non-static methods, you can directly access static methods.

**声明静态方法的语法:**

```
Access_modifier static void methodName()
{ 
     // Method body.
} 
```

类的名称可用于调用或访问静态方法。

**调用静态方法的语法:**

```
className.methodName(); 
```

#### **示例 1:静态方法不能访问实例变量**

JVM 首先运行静态方法，然后创建类实例。因为当使用静态方法时，没有对象是可访问的。静态方法不能访问实例变量。因此，静态方法不能访问类的实例变量。

## 爪哇

```
// Java program to demonstrate that
// The static method does not have
// access to the instance variable

import java.io.*;

public class GFG {
    // static variable
    static int a = 40;

    // instance variable
    int b = 50;

    void simpleDisplay()
    {
        System.out.println(a);
        System.out.println(b);
    }

    // Declaration of a static method.
    static void staticDisplay()
    { 
      System.out.println(a); 
    }

    // main method
    public static void main(String[] args)
    {
        GFG obj = new GFG();
        obj.simpleDisplay();

        // Calling static method.
        staticDisplay();
    }
}
```

**输出**

```
40
50
40
```

#### **例 2:在静态和非静态方法中，静态方法都是直接访问的。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate that
// In both static and non-static methods,
// static methods are directly accessed.

import java.io.*;

public class StaticExample {

    static int num = 100;
    static String str = "GeeksForGeeks";

    // This is Static method
    static void display()
    {
        System.out.println("static number is " + num);
        System.out.println("static string is " + str);
    }

    // non-static method
    void nonstatic()
    {
        // our static method can accessed 
        // in non static method
        display();
    }

    // main method
    public static void main(String args[])
    {
        StaticExample obj = new StaticExample();

        // This is object to call non static function
        obj.nonstatic();

        // static method can called 
        // directly without an object
        display();
    }
}
```

**Output**

```
static number is 100
static string is GeeksForGeeks
static number is 100
static string is GeeksForGeeks
```

#### **为什么使用静态方法？**

1.  访问和更改静态变量和其他非基于对象的静态方法。
2.  实用程序和辅助类经常使用静态方法。

#### **静态方法中的限制:**

1.  静态方法不能使用非静态数据成员或非静态方法，静态方法不能直接调用非静态方法。
2.  在静态环境中，不允许使用这个和 super。

#### **为什么**是 Java **静态的主要方法？**

这是因为对象不需要调用静态方法。如果是非静态函数，JVM 会在调用 main()方法之前先构建一个对象，这会导致额外的内存分配困难。

### **静态方法和实例方法的区别**

<figure class="table">

| 

实例方法

 | 

静态方法

 |
| --- | --- |
| It needs an object of a class. | Object of class is not required. |
| It can access all the properties of a class. | You can only access the static properties of one class. |
| Methods can only be accessed through object references. | Methods can only be accessed by class name. |
| 语法：Objref.methodname（） | 语法:classname。方法名() |
| This is an example of value transfer programming. | Is an example of programming by reference. |

</figure>