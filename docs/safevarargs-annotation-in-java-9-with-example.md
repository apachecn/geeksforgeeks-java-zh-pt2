# @ Java 9 中的 SafeVarargs 注释，示例

> 原文:[https://www . geesforgeks . org/safevarags-annotation-in-Java-9-with-example/](https://www.geeksforgeeks.org/safevarargs-annotation-in-java-9-with-example/)

**@SafeVarargs 注释** : @SafeVarargs 注释引入 JDK 7。@SafeVarargs 注释用于在编译时抑制不安全的操作警告。每当我们在代码中调用具有可变参数的方法时，不安全操作警告就会在编译时出现。@SafeVarargs 注释可以与方法/构造函数一起使用，并且方法应该是最终的或静态的。我们可以对不能被重写的方法使用@SafeVarargs 注释，因为重写方法仍然可以对它们的 Varargs 执行不安全的操作。@ SafeVarargs 注释用于指示方法不会导致堆污染。这些方法被认为是安全的。

在 JDK 9 中，JDK 开发人员扩展了@ safevarags 注释的使用，现在除了 final 或 static 方法之外，我们还可以在 private 方法中使用@ safevarags 注释。这是因为不能重写私有方法。

**什么是不安全操作警告？**

Java 5 引入了 [Varargs](https://www.geeksforgeeks.org/variable-arguments-varargs-in-java/) 的概念，或者说是一个可变长度的方法参数，以及 [Generics](https://www.geeksforgeeks.org/generics-in-java/) ，这次只增加了未检查或者不安全操作的警告。现在的问题是，为什么当我们将方法与 varargs 一起使用或使用泛型时，编译器会抛出警告？当编译器抛出不安全操作警告时，编译器通常会以某种方式要求您更明确地说明类型。

**我们用一些例子来理解这个概念:**

```
// Program to illustrate the unsafe operation warnings
// message with respect to varargs parameter

import java.util.ArrayList;
import java.util.List;

public class Geeksforgeeks {

    // print is a method with variable argument
    private void print(List... topics)
    {
        for (List<String> topic : topics) {
            System.out.println(topic);
        }
    }

    public static void main(String[] args)
    {
        Geeksforgeeks obj = new Geeksforgeeks();
        List<String> list = new ArrayList<String>();
        list.add("OOPS");
        list.add("COLLECTION");
        obj.print(list);
    }
}
```

**编译时控制台:**

```
Note: Geeksforgeeks.java uses unchecked or unsafe operations.
Note: Recompile with -Xlint:unchecked for details.

```

**输出:**

```
[OOPS, COLLECTION]

```

这里我们有一个方法，它的 varargs 类型为 List。但是这里我们没有提到 List 将存储的数据类型。这里编译器会警告你，我不会检查你的代码。我不会检查您将添加到数组列表中的值是否属于任何特定类型。这就是为什么它会在编译时抛出不安全的操作警告。这里编译器想知道类型

```
List<String> geeks = new ArrayList<String>();
```

如果我们用类型创建数组列表，那么编译器在编译时不会抛出任何警告消息。

让我们在使用@SafeVarargs 注释后再次运行相同的代码。

```
// Program to illustrate the
// @SafeVarargs with respect to varargs

import java.util.ArrayList;
import java.util.List;

public class Geeksforgeeks {

    // Here we used @SafeVarargs annotation,
    // now we will not get any unchecked
    // or unsafe operations warning message
    // at compile time
    @SafeVarargs
    private void print(List... topics)
    {
        for (List<String> topic : topics) {
            System.out.println(topic);
        }
    }

    public static void main(String[] args)
    {
        Geeksforgeeks obj = new Geeksforgeeks();
        List<String> list = new ArrayList<String>();
        list.add("OOPS");
        list.add("COLLECTION");
        obj.print(list);
    }
}
```

**输出:**

```
[OOPS, COLLECTION]

```

**注意:**假设如果你想在 JDK 7 或 JDK 8 中运行上述代码，那么你会得到一个编译错误，因为这些增强是在 java 9 之前的 Java 9 中完成的——私有方法不允许用这个注释来标记。

```
// Program to illustrate the unsafe
// operation warnings message
// with respect to Generics

import java.util.ArrayList;
import java.util.List;

public class Geeks<T> {

    private List<T> topics = new ArrayList<>();

    // Here add() is a method with varargs of type T
    // Here T is unknown for
    // the compiler at the compile time
    // That's why It will throw unsafe
    // operation warning message
    public final void add(T... toAdd)
    {
        for (T topic : toAdd) {
            topics.add(topic);
        }
    }

    public static void main(String[] args)
    {
        Geeks geek = new Geeks();
        geek.add("OOPS",
                 "COLLECTIONS",
                 "EXCEPTION-HANDLING");
        System.out.println(geek.topics);
    }
}
```

**编译时控制台:**

```
Note: Geeks.java uses unchecked or unsafe operations.
Note: Recompile with -Xlint:unchecked for details.

```

**输出:**

```
[OOPS, COLLECTIONS, EXCEPTION-HANDLING]

```

让我们在使用@SafeVarargs 注释后再次运行相同的代码。

```
// Program to illustrate the
// @SafeVarargs with respect to Generics

import java.util.ArrayList;
import java.util.List;

public class Geeks<T> {

    private List<T> topics = new ArrayList<>();

    // Here by placing @SafeVarargs annotation
    // to add() method, we are ensuring to the
    // compiler that our action is safe.
    // That's why compiler will not throw
    // any warning message at the compile time.
    @SafeVarargs
    public final void add(T... toAdd)
    {
        for (T topic : toAdd) {
            topics.add(topic);
        }
    }

    public static void main(String[] args)
    {
        Geeks geek = new Geeks();
        geek.add("OOPS",
                 "COLLECTIONS",
                 "EXCEPTION-HANDLING");
        System.out.println(geek.topics);
    }
}
```

**输出:**

```
[OOPS, COLLECTIONS, EXCEPTION-HANDLING]

```