# Java 中的瞬态关键字

> 原文:[https://www.geeksforgeeks.org/transient-keyword-java/](https://www.geeksforgeeks.org/transient-keyword-java/)

**瞬态**是在[序列化](https://www.geeksforgeeks.org/serialization-in-java/)中使用的变量修饰符。在序列化时，如果我们不想在文件中保存特定变量的值，那么我们使用 **transient** 关键字。当 JVM 遇到**瞬态**关键字时，它会忽略变量的初始值，并保存该变量数据类型的默认值。

**瞬态**关键字对于满足安全约束起着重要作用。有各种现实生活中的例子，我们不想把私人数据保存在文件中。 **transient** 关键字的另一个用途是不序列化变量，该变量的值可以使用其他序列化对象或系统(如人的年龄、当前日期等)来计算/导出。
实际上，我们只序列化那些表示实例状态的字段，毕竟序列化就是将对象的状态保存到文件中。序列化时将**瞬态**关键字与类的私有机密字段一起使用是一个好习惯。

```
// A sample class that uses transient keyword to
// skip their serialization.
class Test implements Serializable
{
    // Making password transient for security
    private transient String password;

    // Making age transient as age is auto-
    // computable from DOB and current date.
    transient int age;

    // serialize other fields
    private String username, email;
    Date dob;

    // other code
}
```

**瞬态和静态:**由于**静态**字段不是对象状态的一部分，因此将**瞬态**关键字与静态变量一起使用没有任何用处/影响。但是没有编译错误。

**瞬态和最终:**最终变量直接按其值序列化，因此将最终变量声明为**瞬态**没有任何用处/影响。但是没有编译时错误。

```
// Java program to demonstrate transient keyword
// Filename Test.java
import java.io.*;
class Test implements Serializable
{
    // Normal variables
    int i = 10, j = 20;

    // Transient variables
    transient int k = 30;

    // Use of transient has no impact here
    transient static int l = 40;
    transient final int m = 50;

    public static void main(String[] args) throws Exception
    {
        Test input = new Test();

        // serialization
        FileOutputStream fos = new FileOutputStream("abc.txt");
        ObjectOutputStream oos = new ObjectOutputStream(fos);
        oos.writeObject(input);

        // de-serialization
        FileInputStream fis = new FileInputStream("abc.txt");
        ObjectInputStream ois = new ObjectInputStream(fis);
        Test output = (Test)ois.readObject();
        System.out.println("i = " + output.i);
        System.out.println("j = " + output.j);
        System.out.println("k = " + output.k);
        System.out.println("l = " + output.l);  
        System.out.println("m = " + output.m);
    }
}
```

输出:

```
i = 10
j = 20
k = 0
l = 40
m = 50
```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。