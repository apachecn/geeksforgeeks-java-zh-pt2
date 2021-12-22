# Java 中的接口类型

> 原文:[https://www.geeksforgeeks.org/types-of-interfaces-in-java/](https://www.geeksforgeeks.org/types-of-interfaces-in-java/)

在 Java 中，接口是一种引用类型，类似于只能包含常量、方法签名、默认方法和静态方法以及 ts 嵌套类型的类。在接口中，方法体只存在于默认方法和静态方法中。编写接口类似于编写标准类。尽管如此，类描述属性和内部行为对象，接口包含类实现的行为。另一方面，除非实现接口的类纯粹是抽象的，并且所有接口方法都需要在给定的可用类中定义。

**接口在以下方面类似于类:**

1.  一个接口可以包含任意数量的方法。
2.  接口名称用–()写入文件。接口的名称必须与该 java 程序的文件名匹配。
3.  给定接口的字节码将在–中创建。类文件。
4.  接口出现在包中，它们对应的字节码文件必须类似地处于与包名匹配的结构中。

**如何声明接口？**

interface 关键字用于声明接口。这里我们有一个声明接口的简单例子。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public interface NameOfTheinterface
{

  // Any final, static fields here

  // Any abstract method declaration here

}
//This is Declaration of the interface
```

#### 接口的属性

接口具有以下属性:

*   接口是隐式纯抽象的。
*   声明接口时不需要使用抽象关键字
*   接口中的每个方法也是隐式抽象的，因此不需要抽象关键字
*   接口中的方法在其中是隐式公开的

**示例:** *文件名–Car.java*

## Java 语言(一种计算机语言，尤用于创建网站)

```
// This is Program To implement the Interface
interface car
{
   void display();
}

class model implements car
{
   public void display()
   {

       System.out.println("im a Car");
                     // the code output will print "im a car"
   }

  public static void main(String args[])

    {
   model obj = new model();
   obj.display();
    }
}
```

**Output**

```
im a Car
```

### **接口类型**

1.  功能接口
2.  标记界面

### **1。功能界面:**

*   函数接口是只有一个纯抽象方法的接口。
*   它可以有任意数量的静态和默认方法，甚至还有 **java.lang.Object** 类的公共方法

当一个接口只包含一个抽象方法时，它被称为功能接口。

#### **功能接口示例:**

*   **Runnable** :只包含 run()方法
*   **动作监听器**:只包含已执行的动作()
*   **items listener**:只包含 itemStateChanged()方法

现在，我们将看到一个功能接口的示例–

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// This is Program To implement the Functional Interface

interface Writable
{  
    void write(String txt);  
}  
        // FuninterExp is a Example of Functional Interface
   public class FuninterExp implements Writable
    {  
           public void write(String txt)
        {  
            System.out.println(txt);  
        }  

     public static void main(String[] args)
     {  
        FuninterExp obj = new FuninterExp();  
        obj.write(" GFG - GEEKS FOR GEEKS ");  
     }  
}
```

**Output**

```
 GFG - GEEKS FOR GEEKS 
```

### **2。标记界面:**

*   不包含任何方法、字段、抽象方法和任何常量的接口称为标记接口。
*   另外，如果一个接口是空的，那么它被称为标记接口。
*   可序列化和可克隆接口是标记接口的例子。

**例如:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Simple Example to understand marker interface

public interface interface_name  

    {  
         // empty 
    }
```

对于产生与标记界面相同结果的 **标记界面**有两种选择。

**1)内部标志–**用于代替标记器接口实现任何特定操作。

**2)注释–**通过将注释应用于任何类，我们可以对其执行特定的操作。

#### **内置标记界面**

Java 中有三种类型的内置标记接口。这些是

1.  可克隆接口
2.  可串行化接口
3.  远程接口

**1。可克隆界面**

*   Java 中的可克隆接口也是属于 **java.lang** 包的 Marker 接口。
*   它生成具有不同名称的对象的副本(拷贝)。因此，我们可以在要克隆哪个类对象的类中实现接口。
*   它实现了对象类的 clone()方法。

> **注意–**实现可克隆接口的类必须**通过使用公共方法覆盖克隆()方法**。

**例如:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// This is Program To implement the Clonable Interface
 import java.lang.Cloneable;

 class abc implements Cloneable 
// Here The abc is a class constructor
{
    int x;
    String y;
    // Here The abc is a class constructor
    public abc(int x,String y)
    {
        this.x = x;
        this.y = y;
    }

    protected Object clone()
    throws CloneNotSupportedException

    {
        return super.clone();
    }
}

    public class Test
 {
        public static void main(String[] args)
             throws CloneNotSupportedException
         {

        abc p = new abc(10, "We Are Reading GFG Now");
        abc q = (abc)p.clone();

        System.out.println(q.x);
        System.out.println(q.y);

        }
 }
```

**Output**

```
10
We Are Reading GFG Now
```

**2。可序列化接口:**

*   它是 Java 中的一个标记接口，在 java.io 包中定义。如果我们想使类可序列化，我们必须实现 serializable 接口。如果一个类实现了 Serializable 接口，我们可以序列化或反序列化该类对象的状态。
*   序列化是一种机制，在这种机制中，我们的对象状态从内存中准备好，并写入文件或数据库。
*   反序列化-与序列化相反，序列化意味着从文件或数据库中读取对象状态并将其写回内存，这称为对象的反序列化。

> **序列化–**将对象转换为字节流。
> 
> **反序列化–**将字节流转换为对象。

**3。远程接口:**

*   远程接口是属于 **java.rmi** 包的标记接口。它将一个对象标记为可以从另一台机器的主机访问的远程对象。
*   如果我们想让一个对象远程，那么我们需要实现远程接口。因此，它识别接口。
*   远程接口用于标识其方法可以从非本地虚拟机调用的接口。任何远程对象都必须直接或间接实现这个接口。
*   远程接口是声明将从远程 Java 虚拟机(即 JVM)调用的一组方法的接口