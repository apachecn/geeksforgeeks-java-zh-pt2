# Java 中 Lambda 表达式的序列化

> 原文:[https://www . geesforgeks . org/serialization-of-lambda-expression-in-Java/](https://www.geeksforgeeks.org/serialization-of-lambda-expression-in-java/)

在这里，我们将讨论 java 中的序列化和与 lambda 函数相关的问题，而不是序列化，同时讨论一些方法，由于这些方法，我们需要序列化和正确的实现，就像在干净的 java 程序中一样，使用函数接口完成序列化和反序列化过程。

序列化是将对象的状态写入字节流的过程，这样我们就可以通过网络传输它。如果 lambda 表达式的目标类型和捕获的参数已经序列化，我们可以序列化它。但是，像内部类一样，强烈建议不要序列化 lambda 表达式。由于默认情况下 lambda 函数没有序列化，我们只需将我们的 lambda 转换为 java.io.Serializable。但是 submit 方法需要一个 Runnable 或 Callable 作为参数，而不是 Serializable。因此，我们必须同时将 lambda 转换为两个接口，Runnable 和 Serializable.Java 序列化是一个很好的通用、向后兼容的序列化库。替代品试图解决的两个最常见的问题是性能和跨平台序列化。相比之下，简单的二进制 YAML 序列化使用 348，有更多的选项来优化序列化。这就提出了如何使用替代的、跨平台的或更快的序列化格式来序列化 lambda 的问题。

> **注意:**有必要序列化 lambda 函数，因为序列化 lambda 在许多用例中非常有用，例如持久化配置，或者作为远程资源的访问者模式。

> **图解:**远程访客
> 
> 假设我们想要访问远程地图上的资源。我们可以使用 get/put，但是假设我们只想从 Map 的值中返回一个字段:我们可以传递一个 lambda 作为访问者来提取我们想要的信息。正如您所看到的，添加各种简单的函数，或者调用一个方法来执行您需要的操作是很容易的。唯一的问题是 lambdas 在默认情况下是不可序列化的。

**例**

```java
MapView userMap = Chassis.acquireMap("users", String.class, UserInfo.class);
userMap.put("userid", new UserInfo("User's Name"));

// Print out changes
userInfo.registerSubscriber(System.out::println);

// Obtain just the fullName without downloading the whole object
String name= userMap.applyToKey("userid", u -> u.fullName);

// Increment a counter atomically and trigger
// an updated event printed with the subscriber.

userMap.asyncUpdateKey("userid", ui -> {      
ui.usageCounter++; 
return ui;
});

// Incrementimng counter and return the userid
int count = userMap.syncUpdateKey("userid", 
ui -> { ui.usageCounter++; return ui;}, 
ui -> ui.usageCounter);
```

***serialized lamda*****类**被编译器和库用来确保 Lambda 正确反序列化。使*函数<字符串、字符串> &可序列化*的交集转换改变了 lambda 的底层类型，允许像 Kryo 这样的库正确理解如何反序列化给它的 lambda。

添加& Serializable 的这种额外的强制转换是允许 Kryo 反序列化 lambdas 的一种可能的解决方案。另一种方法是创建一个新的接口，扩展您需要的底层函数类型以及 Serializable。

**布局:**

```java
public class IntersectionCasting {

  public static void main(String[] args) {

    SerializableLambda function = (message) -> "Kryo please serialize this message '" + message + "'";

  }

  interface SerializableLambda extends Function<String, String>, Serializable {}

}
```

现在，为了使我们的应用编程接口中的 Lambdas 可序列化，首先要确保一件事的安全，不幸的是，标准的应用编程接口不能更改，也不能添加子类，但是如果您有自己的应用编程接口，您可以使用可序列化的接口。您的 API 的用户不必明确表示 lambda 是可序列化的。远程实现序列化 lambda，在服务器上执行它，并返回结果。类似地，也有方法将 lambda 作为一个整体应用于地图。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to serialize and deserialize the lambda
// function using a function interface

// Importing input output classes
import java.io.*;
// Importing all function utility classes
import java.util.function.*;

// Interaface
interface MyInterface {

    // Method inside this interface
    void hello(String name);
}

// Class 1
// Helper class implementing above interface
class MyImpl implements MyInterface {

    // Method of this class
    public void hello(String name)
    {
        System.out.println("Hello " + name);
    }
}

// Class 2
// Main class
class GFG {

    // Method 1
    // To Serialize
    private static void serialize(Serializable obj,
                                  String outputPath)
        throws IOException
    {
        File outputFile = new File(outputPath);
        if (!outputFile.exists()) {
            outputFile.createNewFile();
        }
        try (ObjectOutputStream outputStream
             = new ObjectOutputStream(
                 new FileOutputStream(outputFile))) {
            outputStream.writeObject(obj);
        }
    }

    // Method 2
    // To Deserialize
    private static Object deserialize(String inputPath)
        throws IOException, ClassNotFoundException
    {
        File inputFile = new File(inputPath);
        try (ObjectInputStream inputStream
             = new ObjectInputStream(
                 new FileInputStream(inputFile))) {
            return inputStream.readObject();
        }
    }

    // Method 3
    // To Serialize and deserialize lambda functions
    private static void serializeAndDeserializeFunction()
        throws Exception
    {
        Function<Integer, String> fn
            = (Function<Integer, String> & Serializable)(n)
            -> "Hello " + n;
        System.out.println("Run original function: "
                           + fn.apply(10));

        String path = "./serialized-fn";

        serialize((Serializable)fn, path);
        System.out.println("Serialized function to "
                           + path);

        Function<Integer, String> deserializedFn
            = (Function<Integer, String>)deserialize(path);
        System.out.println("Deserialized function from "
                           + path);
        System.out.println("Run deserialized function: "
                           + deserializedFn.apply(11));
    }

    // Method 4
    // To Serialize and deserialize lambda classes
    private static void serializeAndDeserializeClass()
        throws Exception
    {
        String path = "./serialized-class";
        serialize(MyImpl.class, path);
        System.out.println("Serialized class to " + path);

        // Pretending we don't know the exact class of the
        // serialized bits, create an instance from the
        // class and use it through the interface.
        Class<?> myImplClass = (Class<?>)deserialize(path);
        System.out.println("Deserialized class from "
                           + path);
        MyInterface instance
            = (MyInterface)myImplClass.newInstance();
        instance.hello("Java");
    }

    // Method 5
    // Main driver method
    public static void main(String[] args) throws Exception
    {

        // Calling above method 3 and method 4
        // in the main() body
        serializeAndDeserializeFunction();
        serializeAndDeserializeClass();
    }
}
```

**输出:**

```java
Run original function: Hello 10
Serialized function to ./serialized-fn
Deserialized function from ./serialized-fn
Run deserialized function: Hello 11
Serialized class to ./serialized-class
Deserialized class from ./serialized-class
Hello Java
```