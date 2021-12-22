# Java 中的@弃用注释

> 原文:[https://www . geesforgeks . org/the-弃用-注释-in-java/](https://www.geeksforgeeks.org/the-deprecated-annotation-in-java/)

**@弃用的**注释告诉编译器某个方法、类或字段被弃用，如果有人试图使用它，它应该会生成警告。这就是弃用的类或方法。已经不相关了。它是如此不重要，你应该停止使用它，因为它已经被取代，并可能在未来逐步淘汰。

弃用的类或方法就是这样。已经不重要了。事实上，它是如此的不重要，以至于你不应该再使用它，因为它已经被取代了，将来可能会不复存在。因为类的 API(应用程序编程接口)会随着时间的推移而变化，所以 Java 提供了一种表达不赞成的方式。方法被重命名以保持一致性，新的更好的方法被添加，字段被改变。然而，这种变化带来了一个问题。如果您需要保留旧的应用编程接口，直到开发人员过渡到新的应用编程接口，但不希望他们继续针对它进行编程，您可以使用内置注释来反对该项。

现在@ Depricated 注释的使用如下所示:项目的 API 随着时间的推移而演变。随着时间的推移，我们不希望人们再使用某些构造函数、字段、类型或方法。我们可以使用@弃用的注释将这些元素标记为弃用，而不是破坏项目的 API 向后兼容性。@已弃用向其他开发人员指示应避免使用标记的元素。

使用 Java 9，对@弃用的注释做了两个新的增强:

*   **forRemoval** :表示被注释的元素在未来版本中是否会被移除。默认值为假。
*   **从**开始:返回注释元素被弃用的版本。默认值是空字符串。

**如何贬低？**

1.  通过不推荐使用的接口
2.  通过已弃用的类
3.  通过贬低的方法
4.  通过取消成员变量
5.  通过贬低一个构造函数

我们使用**@弃用的**注释来弃用一个方法、类或字段，并在注释部分使用@弃用的 Javadoc 标签来通知开发人员弃用的原因以及可以用什么来代替它。

**1。弃用界面:**

```
@Deprecated

interface GFG {
  // Interface methods
}
```

**2。弃用类**

```
@Deprecated

class GFG {
// Class implementation
}
```

**3。贬低法**

```
class GFG {

  @Deprecated

  // old method
  public void gfgmethod() {}

  // new, alternate method
  public void gfgmethod2() {}
}
```

**4。取消成员变量**

```
class GFG {

  @Deprecated

  public static final int MAX_SIZE  = 1024;
  // new, alternate field
  public static final int MAX_UPLOAD_SIZE = 1024;
}
```

**5。贬低一个构造者**

```
class GFG {

  @Deprecated

  Gfg(String name, int length, int width) {

  }

  // new, alternate constructor
  Gfg(Style style) {

  }
}
```

**实现:**现在让我们用一个干净的 java 程序来实现它们。

**示例 1:** 使用不推荐使用的变量名**。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Illustrating The @Deprecated Annotation
// Using deprecated variable name

// Main class
public class GFG {

    // @deprecated number1 will be replaced by
    // newnum field
    @Deprecated

    // Declaring and initializing integer variables
    int number = 100;
    // New field
    final int newnumber = 100;

    // Main
    public static void main(String a[])
    {
        // Creating an object for the class
        GFG obj = new GFG();

        // Printing the number
        System.out.println(obj.number);
    }
}
```

**Output**

```
100
```

**示例 2:** 使用不推荐使用的方法名称。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Illustrating The @Deprecated Annotation
// Using deprecated method name

// Main class
public class GFG {

    // @deprecated The function oldmethod will be replaced
    //  by new method
    @Deprecated

    // Method 1
    // Old method
    public void oldmethod()
    {

        // Print statement
        System.out.println("This is a deprecated method");
    }

    // Method 2
    // New method
    public void newmethod(String m1)
    {

        // Print statement
        System.out.println(m1);
    }

    // Method 3
    // Main driver method
    public static void main(String a[])
    {

        // Creating an object of class
        GFG obj = new GFG();

        // Now calling the old method
        obj.oldmethod();
    }
}
```

**Output**

```
This is a deprecated method
```

**示例 3:** 使用不推荐使用的方法名和不推荐使用的变量名。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Illustrating The @Deprecated Annotation
// Using deprecated method name
// as well as the deprecated variable name

// Main class
class GFG {

    // @deprecated
    // The old function will be replaced by new one
    @Deprecated

    // Declaring and initializing integer values
    int no = 10;
    final int MAX_NUM = 100;

    @Deprecated

    // Method 1
    // Old method
    public void gfgMsg()
    {

        // Print statement
        System.out.println("This method is deprecated");
    }

    // Method 2
    // New Method
    public void gfgMsg2(String msg, String msg2)
    {

        // Print statement
        System.out.println(msg + msg2);
    }

    // Method 3
    // Main driver method
    public static void main(String a[])
    {

        // Creating an object of class
        GFG obj = new GFG();

        // Now calling the old method
        obj.gfgMsg();

        // Printing the num
        System.out.println(obj.no);
    }
}
```

**Output**

```
This method is deprecated
10
```

**示例 4:** 使用不推荐使用的构造函数和不推荐使用的变量名。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Illustrating The @Deprecated Annotation
// Using deprecated constructor
// as well as the deprecated variable name.

// Main class
public class GFG {

    // @deprecated
    // The field number will be replaced by newnumber field
    @Deprecated

    int number = 10;

    // new field
    final static int newnumber = 10;

    // @deprecated
    // The constructor depexamplewill be replaced by second
    // depexample

    // Old constructor
    GFG(int a, int b, int c)
    {

        // Print statement for old constructor
        System.out.println(
            "This is a deprecated constructor");
    }

    // new constructor
    GFG(float d, int e, float f)
    {

        // Print statement for new constructor
        System.out.println(d + f);
    }

    // Main driver method
    public static void main(String a[])
    {

        // Creating object of class
        GFG obj = new GFG(newnumber, newnumber, newnumber);

        // Print and display the number
        System.out.println(obj.number);
    }
}
```

**Output**

```
This is a deprecated constructor
10
```