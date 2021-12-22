# Java 中的 seriaalvermentuid

> 原文:[https://www.geeksforgeeks.org/serialversionuid-in-java/](https://www.geeksforgeeks.org/serialversionuid-in-java/)

运行时的序列化将一个称为 serialVersionUID 的版本号与每个可序列化的类相关联，该版本号在反序列化期间用于验证序列化对象的发送方和接收方是否为该对象加载了与序列化兼容的类。极客，现在你一定想知道为什么我们使用 SerialVersionUID？

这是因为 SerialVersionUID 用于确保在反序列化期间加载相同的类(在序列化过程中使用的类)。考虑运行下面给出的插图，以更公平地理解[序列化&反序列化](https://www.geeksforgeeks.org/serialization-in-java/)。

插图:

*   假设一个人在英国，另一个人在印度，分别执行序列化和反序列化。在这种情况下，为了验证在印度的接收者是被验证的人，JVM 创建了一个唯一的 ID，称为 **SerialVersionUID** 。
*   在大多数情况下，序列化和反序列化这两项活动都是由一个人在同一个系统和同一个位置完成的。但是在序列化中，发送者和接收者不是同一个人，也就是说，人可能不同，机器或系统可能不同，位置也一定不同。在序列化中，发送方和接收方都应该有。仅在开始时的类文件，即准备进行序列化的人和准备进行反序列化的人应该包含相同的内容。仅在开始时的类文件。

**序列化**在序列化的时候，用每个对象发送方 JVM 都会保存一个**唯一标识符**。JVM 负责根据相应的。发送方系统中存在的类文件。
**反序列化**反序列化时，接收端 JVM 会将与对象相关联的唯一标识与本地类唯一标识进行比较，即 JVM 也会根据相应的。存在于接收系统中的类文件。如果两个唯一标识都匹配，则只执行反序列化。否则，我们将得到运行时异常，表示[无效类异常](https://www.geeksforgeeks.org/serialization-in-java/)。这个唯一标识符只不过是**序列号**。

根据 JVM 生成的默认 SerialVersionUID，还有一些特定的问题关联，如下所示:

1.  就平台和版本而言，发送方和接收方应该使用相同的 JVM。否则，由于序列号不同，接收器无法反序列化。
2.  发送方和接收方应该使用相同的。“类”文件版本。序列化后，如果。' class '文件，则接收器无法反序列化。
3.  为了在内部生成 SerialVersionUID，JVM 可能会使用复杂的算法，这可能会产生性能问题。

**实施:**

我们可以通过配置自己的 SerialVersionUID 来解决上述问题。我们可以配置自己的 SerialVersionUID，为此我们需要 3 个类，如下所示:

*   随机类，包含两个将要序列化的变量，让它成为“极客”
*   将序列化对象的发送方的类
*   要反序列化的接收器端的类

**语法:**

```
private static final long SerialVersionUID=10l;
```

**例 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate Implementation of
// User-defined SerialVersionUID

// Main class
// // Geeks which contains two variable which
// are going to Serialize to
// Illustrate Implementation of Serializable Interface
class Geeks implements Serializable {

    // User-defined SerialVersionUID
    // Custom initialization
    private static final long SerialVersionUID = 10l;
    int i = 10;
    int j = 20;
}
```

**示例 2:** 发送方的类，它将序列化一个对象

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate
// implementation of User-defined
// SerialVersionUID

// Importing required classes
import java.io.*;

// Sender side class which is going to Serialize object
class Sender {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of class Random class which
        // contains two variables which are going to
        // Serialize In simpler words , object of class
        // 'Geeks'
        Geeks g = new Geeks();

        // Here xyz.txt is the file name where the object is
        // going to serialize
        FileOutputStream fos
            = new FileOutputStream("xyz.txt");
        ObjectOutputStream oos
            = new ObjectOutputStream(fos);

        oos.writeObject(g);
    }
}
```