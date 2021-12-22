# Java 中的静态块

> 原文:[https://www.geeksforgeeks.org/static-blocks-in-java/](https://www.geeksforgeeks.org/static-blocks-in-java/)

用更简单的语言来说，每当我们使用[静态关键字](https://www.geeksforgeeks.org/static-keyword-java/)并将其与一个块相关联时，该块就被称为静态块。与 C++不同，Java 支持一种特殊的块，称为静态块(也称为 static 子句)，可用于类的静态初始化。静态块中的这段代码只执行一次:第一次将类加载到内存中。

**Java 中静态块的调用？**

现在该如何调用这个静态块了。因此，为了调用任何静态块，没有指定的方法，因为当类加载到内存中时，静态块会自动执行。请参考下图，了解如何调用静态块。

插图:

```
class GFG {

        // Constructor of this class
        GFG {}
        // Method of this class
        public static void print() { static{} }

        public static void main(String[] args) {

                // Calling of method insside main()
                GFG geeks = new GFG();

                // Calling of constructor inside main()
                new GFG();

                // Calling of static block
                // Nothing to do here as it is called
                // autimatically as class is loaded in memory

        }
}
```

注意:从上图中我们可以看到，一旦类被加载到内存中，静态块就会被自动调用，在 main()内部调用方法和构造函数的情况下，我们没有什么可做的。

**我们可以不创建 main()方法在控制台上打印一些东西吗？**

从面试的角度来看，这是一个非常重要的问题。答案是肯定的，如果我们使用的是 1.6 或之前的版本，我们可以打印，如果在那之后，它会抛出一个。错误。

**示例 1-A:** 运行于 JDK 版本 1.6 的前作

## Java

```
// Java Program Running on JDK version 1.6 of Previous

// Main class
class GFG {

    // Static block
    static
    {
        // Print statement
        System.out.print(
            "Static block can be printed without main method");
    }
}
```

**输出:**

```
Static block can be printed without main method
```

**示例 1-B:** 在 JDK 版本 1.6 及更高版本上运行

## Java

```
// Java Program Running on JDK version 1.6 and Later

// Main class
class GFG {

    // Static block
    static
    {
        // Print statement
        System.out.print(
            "Static block can be printed without main method");
    }
}
```