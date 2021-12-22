# Java 中的随机类与线程本地随机类

> 原文:[https://www . geeksforgeeks . org/random-vs-threadlocalrandom-class-in-Java/](https://www.geeksforgeeks.org/random-vs-threadlocalrandom-classes-in-java/)

java.util 包的 Random Class 用于生成伪随机数流。它使用 48 位种子，通过实现线性同余公式进行修改。线性同余公式的一般形式是 a<sub>n+1</sub>= k * a<sub>n</sub>+c(mod m)，其中 a <sub>0</sub> 是种子，a <sub>1</sub> ，a <sub>2</sub> ，… a <sub>n</sub> ，a <sub>n+1</sub> 是随机数，k，c，m 是常数。

如果我们用相同的种子值创建随机类的两个实例，并为每个实例调用相同的方法序列，它们都将返回相同的数字序列 **s** 。此属性由为此类定义的特定算法强制实施。这些算法使用受保护的实用方法，调用时最多可以给出 32 个伪随机生成的位。随机的例子是线程**–**安全。但是，如果在线程间使用相同的实例，它们可能会受到争用的影响，从而导致性能下降。随机实例不是加密安全的，因此不应用于安全敏感的应用程序。

**语法:**

```java
public class Random extends Object implements Serializable
```

让我们举个例子，在下面给出的程序中，我们有三个 Random 类的实例。前两个具有传入其构造函数的相同种子值。这导致当我们使用 Random 类的 nextInt()方法时生成相同的数字。但是，当我们更改种子的值并使用它创建第三个实例时，生成的数字是不同的。这个例子清楚地展示了上述事实，即如果使用相同的种子值并且对两者使用相同的方法，那么实例生成相同的数字序列。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Random class

// Importing Random class from java.util utility package
import java.util.Random;

// Class
// Main clas extending to parent Random class
public class RandomNumbers extends Random {

    // Main driver method
    public static void main(String[] args)
    {

        // Initialise a seed value
        long seed = 18;

        // Create an instance of Random using the seed value
        Random r1 = new Random(seed);

        // Printing the primitive datatype-integer
        // by parsing using nextInt() method
        System.out.println(r1.nextInt());

        // Create a different instance of Random using the
        // same seed value
        Random r2 = new Random(seed);

        // Again, printing the primitive datatype-integer
        // by parsing using nextInt() method
        System.out.println(r2.nextInt());

        // Change the seed value to
        // some other random value
        seed = 34;

        // Create a new instance using the updated seed
        // value
        Random r3 = new Random(seed);

        // Lastly printing the primitive datatype-integer
        // by parsing using nextInt() method
        System.out.println(r3.nextInt());
    }
}
```

**Output**

```java
-1148559096
-1148559096
-1167027043
```

现在来看下一个类，也就是我们的 ThreadLocalRandom 类

java.util 包中的线程本地随机类也用于生成伪随机数流。它是上面讨论的随机类的一个子类。顾名思义，这个类生成独立于当前线程的随机数。ThreadLocalRandom 是使用内部生成的种子值初始化的，否则该种子值是不可修改的。使用 ThreadLocalRandom 而不是 Random 的共享实例将导致较低的争用和开销。ThreadLocalRandom 就像它的父类一样，在加密方面是不安全的。

**语法:**

```java
public class ThreadLocalRandom extends Random 
```

**实现:**让我们来看一个场景，我们在 main 中创建两个简单的线程。在 run()方法内部我们称之为***threadlocalrandom . current . nextint()***。两个线程使用相同的种子值，即 10，但给出不同的结果，因为对 *nextInt()* 的调用是由线程执行隔离的。

**示例**

## Java

```java
// Java Program to Illustrate ThreadLocalRandom class

// Importing ThreadLocalRandom class from utility package
// named java.util.concurrent package
import java.util.concurrent.ThreadLocalRandom;

// Class 1
// Main class extending parent class- Thread
class ThreadLocalRandomNumbers extends Thread {

    // Method 1
    // The run() method of the Thread class
    // Must be defined by every class that extends it
    public void run()
    {

        // Try block to check for exceptions
        try {

            // Initializing a seed value to
            // some random integer value
            int seed = 10;

            // Getting the current seed by
            // calling over ThreadLocalRandom class and
            // storing it in a integer variable
            int r
                = ThreadLocalRandom.current().nextInt(seed);

            // Printing the generated number r
            // The thread id is obtained using getId()
            System.out.println(
                "Thread " + Thread.currentThread().getId()
                + " generated " + r);
        }

        // Catch block to catch the exceptions
        catch (Exception e) {

            // Display message on the console if
            // the exception/s occur
            System.out.println("Exception");
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Create two threads
        ThreadLocalRandomNumbers t1
            = new ThreadLocalRandomNumbers();
        ThreadLocalRandomNumbers t2
            = new ThreadLocalRandomNumbers();

        // Starting th above created threads
        // using the start() method
        t1.start();
        t2.start();
    }
}
```

**输出**

```java
Thread 12 generated 7
Thread 11 generated 0
```

现在我们已经讨论完了这两个课程，并且对它们都有了足够的了解。现在总结一下它们之间的区别来结束这篇文章。

<figure class="table">

|  | **Thread local Random** |
| --- | --- |
| If different threads use the same random instance, it will lead to contention and subsequent performance degradation. | There is no contention because the generated random number is local to the current thread. |
| Use linear congruence formula to modify its seed value. | Random generator uses internally generated seeds for initialization. |
| It is useful in applications where each thread has its own set of random instances to use. | It is suitable for applications where multiple threads in the thread pool use random numbers in parallel. |
| This is the parent class. | This is the Child class. |

</figure>