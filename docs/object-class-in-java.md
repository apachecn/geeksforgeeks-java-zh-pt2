# Java 中的对象类

> 原文:[https://www.geeksforgeeks.org/object-class-in-java/](https://www.geeksforgeeks.org/object-class-in-java/)

**对象**类存在于 **java.lang** 包中。Java 中的每个类都是直接或间接从**对象**类派生出来的。如果一个类没有扩展任何其他类，那么它是**对象**的直接子类，如果扩展了其他类，那么它是间接派生的。因此，对象类方法对所有的 Java 类都是可用的。因此，在任何 Java 程序中，对象类都是继承层次的根。

**使用对象类方法**

**对象**类有方法:

1.  **toString()** : toString()提供对象的字符串表示，用于将对象转换为 String。Object 类的默认 toString()方法返回一个字符串，该字符串由对象作为实例的类的名称、at 符号字符“@”和对象哈希代码的无符号十六进制表示形式组成。换句话说，它被定义为:

```java
// Default behavior of toString() is to print class name, then
// @, then unsigned hexadecimal representation of the hash code
// of the object
public String toString()
{
    return getClass().getName() + "@" + Integer.toHexString(hashCode());
}
```

1.  总是建议覆盖 **toString()** 方法来获得我们自己的对象的字符串表示。有关重写 toString()方法的更多信息，请参考–[在 Java 中重写 toString()](https://www.geeksforgeeks.org/overriding-tostring-method-in-java/)
    **注意:**每当我们试图打印任何对象引用时，都会在内部调用 toString()方法。

```java
Student s = new Student();

// Below two statements are equivalent
System.out.println(s);
System.out.println(s.toString());
```

2.  **hashCode()** :对于每个对象，JVM 都会生成一个唯一的编号，这个编号就是 hashCode。它为不同的对象返回不同的整数。关于这个方法一个常见的误解是 hashCode()方法返回对象的地址，这是不正确的。它通过算法将对象的内部地址转换成整数。hashCode()方法是**原生的**，因为在 Java 中不可能找到对象的地址，所以它使用 C/C++这样的原生语言来找到对象的地址。
    **使用 hashCode()方法:**返回一个哈希值，用于搜索集合中的对象。JVM(Java Virtual Machine)使用 hashcode 方法，同时将对象保存到哈希相关的数据结构中，如 HashSet、HashMap、Hashtable 等。基于哈希代码保存对象的主要优点是搜索变得容易。
    **注意:**需要覆盖 **hashCode()** 方法，以便为每个对象生成一个唯一的编号。例如，对于学生类，我们可以从 hashCode()方法返回学生的人数，因为它是唯一的。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of
// hashCode() and toString()
public class Student
{
    static int last_roll = 100;
    int roll_no;

    // Constructor
    Student()
    {
        roll_no = last_roll;
        last_roll++;
    }

    // Overriding hashCode()
    @Override
    public int hashCode()
    {
        return roll_no;
    }

    // Driver code
    public static void main(String args[])
    {
        Student s = new Student();

        // Below two statements are equivalent
        System.out.println(s);
        System.out.println(s.toString());
    }
}
```

1.  输出:

```java
Student@64
Student@64
```

1.  注意 4 * 16<sup>0</sup>+6 * 16<sup>1</sup>= 100

2.  **等于(Object obj)** :将给定对象与“this”对象(调用方法的对象)进行比较。它给出了一种比较对象是否相等的通用方法。建议覆盖 **equals(Object obj)** 方法，得到我们自己的 Objects 相等条件。有关重写 equals(Object obj)方法的更多信息，请参考–[在 Java 中重写 equals 方法](https://www.geeksforgeeks.org/overriding-equals-method-in-java/)
    **注意:**每当该方法被重写时，通常需要重写 **hashCode()** 方法，以便维护 hashCode 方法的一般约定，该约定规定相等的对象必须具有相等的哈希代码。

3.  **getClass()** :返回“this”对象的类对象，用于获取对象的实际运行时类。它也可以用来获取这个类的元数据。返回的类对象是由所表示的类的静态同步方法锁定的对象。因为这是最终决定，所以我们不会推翻它。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of getClass()
public class Test
{
    public static void main(String[] args)
    {
        Object obj = new String("GeeksForGeeks");
        Class c = obj.getClass();
        System.out.println("Class of Object obj is : "
                           + c.getName());
    }
}
```

1.  输出:

```java
Class of Object obj is : java.lang.String
```

1.  **注意:**加载完. class 文件后，JVM 会在 Heap 区域创建一个类型为 *java.lang.Class* 的对象。我们可以使用这个类对象来获取类级别的信息。广泛应用于[反射](https://www.geeksforgeeks.org/reflection-in-java/)

2.  **finalize()** 方法:就在垃圾收集对象之前调用该方法。当垃圾收集器确定不再有对对象的引用时，它由对象上的[垃圾收集器](https://www.geeksforgeeks.org/garbage-collection-java/)调用。我们应该重写 finalize()方法来释放系统资源，执行清理活动并最小化内存泄漏。例如，在销毁 Servlet 对象 web 容器之前，总是调用 finalize 方法来执行会话的清理活动。
    **注意:** finalize 方法只在一个对象上调用**一次**，即使该对象有资格进行多次垃圾收集。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of finalize()
public class Test
{
    public static void main(String[] args)
    {
        Test t = new Test();
        System.out.println(t.hashCode());

        t = null;

        // calling garbage collector
        System.gc();

        System.out.println("end");
    }

    @Override
    protected void finalize()
    {
        System.out.println("finalize method called");
    }
}
```

1.  输出:

```java
366712642
finalize method called
end
```

2.  **clone()** :返回一个和这个对象完全一样的新对象。关于克隆()方法，请参考[克隆()](https://www.geeksforgeeks.org/clone-method-in-java-2/)T4】
3.  其余三种方法 **wait()** 、 **notify()** 、 **notifyAll()** 都与并发有关。详见[Java 线程间通信](https://www.geeksforgeeks.org/inter-thread-communication-java/)。