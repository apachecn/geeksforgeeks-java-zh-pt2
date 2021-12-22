# Java 中的用户定义包

> 原文:[https://www . geesforgeks . org/用户定义的 java 包/](https://www.geeksforgeeks.org/user-defined-packages-in-java/)

**包**在 Java 中是封装一组类、接口和子包的机制。在 Java 中，它用于使类、接口、枚举和注释的搜索/定位和使用更加容易。也可以认为是数据封装。换句话说，我们可以说一个包是一组相关类的容器，其中一些可访问的类被公开，而另一些被保留用于内部目的。

### 包的类型

包分为两部分。这些是:

*   **Built-in package:** A package already defined, such as java.io.*, java. Lang. * Wait. , known as the built-in package.
*   **User-defined package:** As the name implies, a user-defined package in Java is essentially a programmer-defined package. Whenever we want to add a class to a package, we must mention the package name and the keyword "package" at the top of the program.

### 用户定义的包

**用户定义的**包是由开发人员设计或创建的包，用于对类和包进行分类。它们与 java 提供的内置功能非常相似。它可以导入到其他类中，并像我们使用内置包一样使用。但是如果我们省略 package 语句，类名将被放入缺省包中，缺省包没有名称。

要创建包，我们应该使用 package 关键字。

**语法:**

```
package package-name;
```

### 创建用户定义包的步骤

**步骤 1:** 在 java 类中创建包。格式非常简单容易。只需按名称写一个包。

```
package example1;
```

**步骤 2:** 在 java 包中包含类，但是要记住类只有一个包声明。

```
package example1;

class gfg {
   public static void main(Strings[] args){
     -------function--------
   }
} 
```

**第三步:**现在自定义包创建成功，我们可以将其导入到其他包中并使用它的功能

> **注意:**如果我们没有在包中编写任何类，它将被放置在当前的默认包中。

在下面提到的例子中，第一个例子我们将创建一个用户定义的包名“example”，在这个包下我们有一个名为“gfg”的类，它有一个打印消息的函数。在第二个示例中，我们将导入用户定义的包名“示例”，并使用该包中的函数。

**示例 1:** 在本例中，我们将创建一个用户定义的包和函数来为用户打印消息。

## 爪哇

```
// Java program to create a user-defined
// package and function to print
// a message for the users.

package example;

public class gfg {

    public void show()
    {
        System.out.println("Hello geeks!! How are you?");
    }

    public static void main(String args[])
    {
        gfg obj = new gfg();
        obj.show();
    }
}
```

**输出 1:**

```
Hello geeks!! How are you?
```

**例 2:**

在下面提到的示例中，我们将导入在上面的示例中创建的用户定义的包“示例”。并使用该功能打印消息。

## 爪哇

```
import example.gfg;

public class GFG {
    public static void main(String args[])
    {
        gfg obj = new gfg();
        System.out.println(obj.show());
    }
}
```

**输出 2:**

```
Hello geeks!! How are you?
```

在上面的例子中，首先，我们创建了一个用户定义的包名“example”，在这个包下我们有一个类名“gfg”，它由一个用来打印问候消息的函数组成。在编译和执行代码后，我们会得到消息“你好，极客们！！你好吗？”。在下一个例子中，我们导入了用户定义的包名“example”，并使用了 show 函数。所以在这两个程序的输出中，你可以看到我们有一个问候信息。