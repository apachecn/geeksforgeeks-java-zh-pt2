# Java 异常处理中的嵌套尝试块

> 原文:[https://www . geesforgeks . org/nested-try-blocks-in-exception-handling-in-Java/](https://www.geeksforgeeks.org/nested-try-blocks-in-exception-handling-in-java/)

在 [Java](https://www.geeksforgeeks.org/java/) 中，我们可以在一个试块内使用一个[试块](https://www.geeksforgeeks.org/exceptions-in-java/)。每次输入 try 语句时，该异常的上下文都会被推送到堆栈上。下面给出了一个嵌套尝试的例子。
在本例中，内部 try block(或 try-block2)用于处理算术异常，即被零除。之后，外部 try 块(或 try-block)处理 ArrayIndexOutOfBoundsException。

**例 1:**

```java
class NestedTry {

    // main method
    public static void main(String args[])
    {
        // Main try block
        try {

            // initializing array
            int a[] = { 1, 2, 3, 4, 5 };

            // trying to print element at index 5
            System.out.println(a[5]);

            // try-block2 inside another try block
            try {

                // performing division by zero
                int x = a[2] / 0;
            }
            catch (ArithmeticException e2) {
                System.out.println("division by zero is not possible");
            }
        }
        catch (ArrayIndexOutOfBoundsException e1) {
            System.out.println("ArrayIndexOutOfBoundsException");
            System.out.println("Element at such index does not exists");
        }
    }
    // end of main method
}
```

**Output:**

```java
ArrayIndexOutOfBoundsException
Element at such index does not exists

```

每当一个 try 块没有针对特定异常的 catch 块时，就检查父 try 块的 catch 块是否有该异常，如果找到匹配，就执行该 catch 块。

如果没有任何 catch 块处理该异常，那么 Java 运行时系统将处理该异常，并且将为该异常显示系统生成的消息。

**例 2:**

```java
class Nesting {
    // main method
    public static void main(String args[])
    {
        // main try-block
        try {

            // try-block2
            try {

                // try-block3
                try {
                    int arr[] = { 1, 2, 3, 4 };
                    System.out.println(arr[10]);
                }

                // handles ArithmeticException if any
                catch (ArithmeticException e) {
                    System.out.println("Arithmetic exception");
                    System.out.println(" try-block1");
                }
            }

            // handles ArithmeticException if any
            catch (ArithmeticException e) {
                System.out.println("Arithmetic exception");
                System.out.println(" try-block2");
            }
        }

        // handles ArrayIndexOutOfBoundsException if any
        catch (ArrayIndexOutOfBoundsException e4) {
            System.out.print("ArrayIndexOutOfBoundsException");
            System.out.println(" main try-block");
        }
        catch (Exception e5) {
            System.out.print("Exception");
            System.out.println(" handled in main try-block");
        }
    }
}
```

**Output:**

```java
ArrayIndexOutOfBoundsException main try-block

```