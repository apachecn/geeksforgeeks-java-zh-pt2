# 哪些 Java 类型可以实现接口？

> 原文:[https://www . geesforgeks . org/哪些-Java-type-可以-实现-接口/](https://www.geeksforgeeks.org/which-java-types-can-implement-interfaces/)

在 Java 中没有多重继承的概念，但是借助接口我们可以实现多重继承。接口是定义的命名集合。(未实施)

Java 中的接口是一种特殊的类。像类一样，接口包含方法和成员；与类不同，在接口中，所有成员都是最终的，所有方法都是抽象的。

> //界面定义
> 
> //我们用接口关键字 来声明接口
> 
> 界面<界面 _ 名称> {
> 
> 变量申报；//
> 
> 方法申报；//不实现它们，总是公开和抽象的。
> 
> }
> 
> //实现接口的类
> 
> 公开课<课 _ 名>实行<接口 _ 名> {
> 
> //声明我的接口类的方法应该由实现它的类来实现。
> 
> }

*   我们不能用 java 实例化接口，这意味着我们不能创建接口类的对象。
*   实现接口的类必须为其所有方法提供实现，除非它是抽象类。
*   默认情况下，接口的任何属性都是公共的、静态的和最终的。因此，没有必要为属性提供访问修饰符，但是如果它符合，也不要抱怨它。
*   默认情况下，方法是隐式抽象和公开的，这完全有意义，因为方法没有主体，因此子类可以提供方法实现。
*   静态方法不能在接口中声明——这些方法从来不是抽象的，也不表达对象的行为

**Java 类型实现接口**

主要有 5 种 java 类型可以实现下面列出的接口，我们将在后面深入探讨如下:

1.  Java 类
2.  Java 抽象类
3.  Java 嵌套类
4.  Java 枚举
5.  Java 动态代理

**类型 1:** Java 类

当一个类实现一个接口时，本质上是签署一个契约。要么类必须实现接口及其超接口中声明的所有方法，要么类必须声明为抽象的。

若要声明实现接口的类，请在类声明中包含 implements 关键字。您的类可以实现多个接口，因此 implements 关键字后面是一个逗号分隔的类实现的接口列表。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program illustrating Java Class implementing
// Interfaces

// Importing I/O classes
import java.io.*;

interface Animal {

    // final public static int x = 4;
    // public, static and final
    int x = 4;

    // Public and abstract
    void sound();
}

// Class implementing interface
class Chicks implements Animal {

    // Implementing the abstract method
    public void sound() { System.out.println("cheep"); }

    // Main driver method
    public static void main(String[] args)
    {
        Chicks c = new Chicks();
        c.sound();
        System.out.println("The value of x = " + x);
    }
}
```

**Output**

```java
cheep
The value of x = 4

```

**类型 2:** Java 抽象类

接口和[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)在很多方面是相似的，但是一个抽象类允许单个继承，而接口允许多个继承。如果一个类包含一个接口，但是没有完全实现接口所需的方法，那么这个类必须声明为一个抽象类。

当我们实现抽象类的接口时，这意味着抽象类继承了接口的所有方法。没有必要在抽象类中实现所有的方法，但是，它涉及到抽象类(也是通过继承)，所以抽象类可以将一些方法留在接口中而不在这里实现。但是，当这个抽象类被某个类继承时，它们必须实现抽象类中所有未实现的方法。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program illustrating Java Abstract Class
// implementing Interfaces

// Importing I/O classes
import java.io.*;

interface Animal {
    public void sound();
    public void breed();
}

abstract class Cat implements Animal {

    // Note: It is is not necessary to implement
    // all methods of interface class

    public void sound() { System.out.println("meow"); }
}

public class Cat1 extends Cat {
    public void breed() { System.out.println("Ragdoll"); }
}

class Main {
    public static void main(String[] args)
    {
        Cat1 c = new Cat1();
        c.breed();
        c.sound();
    }
}
```

**Output**

```java
Ragdoll
meow

```

**类型 3:** Java 嵌套类

Java 能够在接口中嵌套一个类。嵌套类是隐式公共的和静态的。在接口内部嵌套类可能很有用，尤其是当封闭接口和封闭类之间存在关系时。在接口中嵌套类可以提高源代码的可读性。具有相同名称的类和接口，嵌套也可以帮助您避免两者之间的名称冲突。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program illustrating Java Nested Classes
// implementing Interfaces

// Importing I/O classes
import java.io.*;

interface Animal {

    // Nested class
    public class Type {

        public static void animal()
        {
            System.out.println("The animal is cat");
        }
    }

    public void breed();
    public void sound();
}

public class Cat implements Animal {

    // Method 1
    public void breed() { System.out.println("Munchkin"); }

    // Method 2
    public void sound() { System.out.println("Meow"); }
}

// Main class 
class MainClass {
    public static void main(String args[])
    {
        Cat c = new Cat();

        // Calling the nested class
        Animal.Type.animal();
        c.breed();
        c.sound();
    }
}
```

**Output**

```java
The animal is cat
Munchkin
Meow

```

**类型 4:** Java 枚举

枚举可以实现 Java 中的任何接口。因为 enum 是一种类型，类似于任何其他类和接口，所以它可以用 java 实现任何接口。在某些情况下，这为使用枚举实现其他行为提供了很大的灵活性。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program illustrating Java Enum class
// implementing Interfaces

// Importing I/O classes
import java.io.*;
// interface class
interface Cat {
    public void breed();
}

// Class 1
// Enum class
enum Breed implements Cat {

    Siamese,
    Persian,
    Bengal,
    Burmese;

    public void breed()
    {
        System.out.print("The breed is " + this);
    }
}

// Class 2
// Main class
public class MainClass {

    // main driver method
    public static void main(String args[])
    {
        Breed.Persian.breed();
    }
}
```

**Output**

```java
The breed is Persian
```

**类型 5:** Java 动态代理

代理通过代理对象间接调用对象方法。java.lang.reflect API 提供了一个作为 Proxy 的类和一个作为 InvocationHandler 的接口。这两个应用编程接口一起创建了一个[动态代理类。](https://www.geeksforgeeks.org/java-lang-reflect-proxy-class-in-java/)代理类根据给定的参数创建动态代理类。InvocationHandler 调用动态代理类的方法。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program illustrating Java Dynamic Proxy Class
// implementing Interfaces

package javaInterface;
// Importing I/O classes
import java.io.*;
// Interface
interface Animal {
    public void breed();
    public void sound();
}
// Class 1
// Class implementing interface
class Cat implements Animal {
    public void breed() { System.out.println("Ragdoll"); }
    public void sound() { System.out.println("meow"); }
}
// Class 2
// InvocationHandler that simply passes every method call
// through to an instance:
import java.lang.reflect.InvocationHandler;
import java.lang.reflect.Method;
class LoggingHandler implements InvocationHandler {
    private final Object target;
    private Map<String, Integer> calls = new HashMap<>();
    public LoggingHandler(Object target)
    {
        this.target = target;
    }
    public Object invoke(Object proxy, Method method,
                         Object[] args) throws Throwable
    {
        String name = method.getName();
        if (name.contains("toString")) {
            return calls.toString();
        }
        calls.merge(name, 1, Integer::sum);
        return method.invoke(target, args);
    }
}
// Class 3
// create a proxy using this invocation handler, we use the
// newProxyInstance
// static utility method on the java.reflection.Proxy class:
import java.lang.reflect.Proxy;
import java.util.HashMap;
import java.util.Map;

class MainClass {
    @SuppressWarnings("unchecked")
    public static <T> T withLogging(T target, Class<T> itf)
    {
        return (T)Proxy.newProxyInstance(
            itf.getClassLoader(), new Class<?>[] { itf },
            new LoggingHandler(target));
    }
    public static void main(String args[])
    {
        Cat c = new Cat();
        Animal logged = withLogging(c, Animal.class);
        logged.breed();
        logged.sound();
        System.out.println(logged);
    }
}
```

输出:

```java
Ragdoll
meow
{sound=1, breed=1}
```