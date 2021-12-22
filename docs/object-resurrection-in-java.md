# Java 中的对象复活

> 原文:[https://www.geeksforgeeks.org/object-resurrection-in-java/](https://www.geeksforgeeks.org/object-resurrection-in-java/)

在带有垃圾收集的面向对象编程语言中，对象复活是指对象在对象销毁过程中复活，作为正在执行的终结器的副作用。

对象复活会导致许多问题，特别是即使没有发生对象复活的可能性也会使垃圾收集变得更加复杂和缓慢，这也是不鼓励终结器的一个主要原因。语言以各种方式处理对象复活，作为这些问题的解决方案。在极少数情况下，对象复活用于实现某些设计模式，特别是对象池，而在其他情况下，复活是由终结器中的错误导致的不希望的错误，通常不鼓励复活。

当一个对象不再能从程序中访问并可能被收集(销毁和重新分配)时，它就变成了垃圾。然后，在对象销毁期间，在垃圾收集器解除分配对象之前，可以运行 finalize 方法，这又可以通过创建对垃圾对象的引用来使垃圾对象再次可达。

如果一个复活的对象后来被取消引用，它再次符合垃圾收集的条件。但是，这一次 [*finalize()方法*](https://www.geeksforgeeks.org/finalize-method-in-java-and-how-to-override-it/) 不会被再次调用，因为 Java 最多只调用一次终结器。在后半部分中，为了便于理解，输出通过一个视频图示来说明，该图示说明了输出是如何保留在屏幕上的。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Object Resurrection

// Importing all utility classes from java.util package
// Importing all input output classes from java.io package
import java.io.*;
import java.util.*;

// Main class
public class GFG {

    // Member variable of this class
    private int num;

    // Constructor of the class
    public GFG(int num)
    {

        // This keyword refers to current instance
        this.num = num;
    }

    // Creating an ArrayList class object
    // Declaring object of class type
    static final ArrayList<GFG> ar = new ArrayList<GFG>();

    // Method 1 (protected)
    protected void finalize() throws Throwable
    {

        System.out.println("Resurrect " + num);

        // Adding the current instance to object
        // using this operator
        ar.add(this);
    }

    // Method 2
    // Standard way to convert to string type
    public String toString()
    {

        return "Element{"
            + "num=" + num + '}';
    }

    // Method 3
    // Main driver method
    public static void main(String[] args)
        throws InterruptedException
    {

        // Iterating using nested for loops
        for (int i = 0; i < 3; i++)
            ar.add(new GFG(i));
        for (int j = 0; j < 5; j++) {

            // print the element in the object
            System.out.println("Elements : " + ar);

            // Clearing off elements using clear() method
            ar.clear();

            // Garbage collector
            System.gc();

            // Making the thread to sleep for a 1/10 sec
            // using the sleep() method
            Thread.sleep(500);
        }
    }
}
```

**输出:**

```java
Elements : [Element{num=0}, Element{num=1}, Element{num=2}]                                                                            
Resurrect 2                                                                                                                            
Resurrect 1                                                                                                                            
Resurrect 0                                                                                                                            
Elements : [Element{num=2}, Element{num=1}, Element{num=0}]                                                                            
Elements : []
Elements : []
Elements : []
```

**输出说明:**

元素被添加到集合中一次，并通过 finalize 方法复活一次。当它们被第二次收集时，它们已经被标记为完成，并且不再排队。借助视频输出进行演示。

<video class="wp-video-shortcode" id="video-602365-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210511162751/Resurrection.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210511162751/Resurrection.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210511162751/Resurrection.mp4)</video>