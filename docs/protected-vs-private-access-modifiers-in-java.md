# Java 中受保护与私有访问修饰符

> 原文:[https://www . geesforgeks . org/protected-vs-private-access-modifiers-in-Java/](https://www.geeksforgeeks.org/protected-vs-private-access-modifiers-in-java/)

[访问修饰符](https://www.geeksforgeeks.org/access-modifiers-java/)是代码中决定变量范围的那些元素。正如我们所知，有三种可用的访问修饰符，即公共的、受保护的和私有的。让我们看看受保护和私有访问修饰符之间的区别。

![](img/00bb5e2b7db16215bebe659d08f86b68.png)

**访问修饰符 1:** 受保护

声明为受保护的方法或变量可以在同一个包或不同的包中访问。通过使用受保护的关键字，我们可以声明受保护的方法/变量。

**语法:**

```java
protected void method_name(){

......code goes here..........

}
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Protected Access Modifier 

// Importing input output classes
import java.io.*;

// Main class 
public class Main {

  // Input custom string 
  protected String name = "Geeks for Geeks";

  // Main driver method 
  public static void main(String[] args) {

    // Creating an object of Main class 
    Main obj1 = new Main();

    // Displaying the object content as created
    // above of Main class itself  
    System.out.println( obj1.name );

}
}
```

**Output**

```java
Geeks for Geeks
```

**访问修饰符 2:** 私有

声明为私有的方法或变量只能在声明它们的类中访问。通过使用 ***【私有】*** 关键字我们可以设置方法/变量私有。

**语法:**

```java
private void method_name(){

......code goes here..........

}
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Private Access Modifier

// Importing input output classes
import java.io.*;

// Main class
public class Main {

    // Input custom string
    private String name = "Geeks for Geeks";

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of Main class
        Main obj1 = new Main();

        // Displaying the object content as created
        // above of Main class itself
        System.out.println(obj1.name);
    }
}
```

**Output**

```java
Geeks for Geeks
```

现在，在了解了它们的内部工作机制之后，让我们来总结一下这些访问修饰符之间的主要区别。

<figure class="table">

|  | **私人** |
| --- | --- |
| The key word used is' protected' | The keyword used is' private' |
| Protected can be used within the same class. | Private can be used within the same class. |
| Protected can be used in the same steamed stuffed bun class. | Private cannot be used in the same steamed stuffed bun class. |
| Protected can be used in different steamed stuffed bun classes. | Private cannot be used in different steamed stuffed bun classes. |
| Protected can package non-subclasses | Private cannot be used for different package non-subclasses |

</figure>