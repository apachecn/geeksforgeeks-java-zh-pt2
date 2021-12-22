# Java 序列化中的对象图

> 原文:[https://www . geesforgeks . org/object-graph-Java-serialization/](https://www.geeksforgeeks.org/object-graph-java-serialization/)

你们中的大多数人肯定都知道涉及单个对象的[序列化](https://www.geeksforgeeks.org/serialization-in-java/)，但是你们有没有想过如果该对象也引用了其他对象呢？会连载吗？引用对象会被序列化吗？
这些问题的答案是肯定的，你不必显式序列化引用对象。让我们看看这是如何实现的。

**什么是对象图？**
对象图是一组将被自动序列化的对象，如果包含对它们的引用的对象被序列化。
换句话说，我们可以说，当我们序列化任何对象时，如果它包含任何其他对象引用，那么 JVM 会序列化该对象及其对象引用。
让我们借助一个简单的例子来更清楚地说明这一点。

```
// Java program to demonstrate how serializing 
// an object serializes other reference objects.
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.ObjectInputStream;
import java.io.ObjectOutputStream;
import java.io.Serializable;

// Class Serial1 contains reference to object 
// of class Serial2. 
class Serial1 implements Serializable {
     Serial2 s2 = new Serial2(); 
}

// Class Serial2 contains reference to object 
// of class Serial3. 
class Serial2 implements Serializable {
     Serial3 s3 = new Serial3(); 
}

// A reference of this class is present in Serial2
class Serial3 implements Serializable {
     int i = 10;
     int j = 20;
}

class DemoSerialize {

     public static void main(String args[]) throws Exception {

     // Creating object of class Serial1
     Serial1 s1 = new Serial1();

     // Serializing object of class Serial1
     // Saving object in file
     FileOutputStream fos = new FileOutputStream("abc.ser");
     ObjectOutputStream oos = new ObjectOutputStream(fos);

     // Method for serializing object of class Serial1
     oos.writeObject(s1);

     // Close streams once serialization is done
     fos.close();
     oos.close();

     // De-Serializing object of class Serial1

     // Reading object from file
     FileInputStream fis = new FileInputStream("abc.ser");
     ObjectInputStream ois = new ObjectInputStream(fis);

     // Method for de-serializing object of class Serial1     
     Serial1 serobject = (Serial1) ois.readObject();

     // Close streams once de-serialization is done
     fis.close();
     ois.close();

     // Printing values of i and j after Serialization
     System.out.println("Value of i after Serialization" + 
                               " is " + serobject.s2.s3.i);
     System.out.println("Value of j after Serialization" + 
                                " is "+serobject.s2.s3.j);
  }
}
```

输出:

```
Value of i after Serialization is 10
Value of j after Serialization is 20

```

**注**:在对象图中，每个对象都应该是可序列化的。如果至少有一个对象是不可序列化的，那么我们将得到运行时执行，说**非序列化执行**。

本文由 **Somya Garg** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。