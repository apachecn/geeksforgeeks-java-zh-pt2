# Java 中的 NumberFormat 等于()方法，示例

> 原文:[https://www . geesforgeks . org/number format-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-equals-method-in-java-with-examples/)

**equals()** 方法是**[Java . text . number format](https://www.geeksforgeeks.org/numberformat-class-java/)**的内置方法，接受一个作为对象的参数，如果这个参数对象与对象相同，则返回 true，否则返回 false。

**语法** :

```java
public boolean equals(Object arg)
```

**参数**:该函数接受单个强制参数**参数**，该参数指定要比较的对象。

**返回值**:该函数返回一个布尔值。如果两个对象相同，则返回 true，否则返回 false。

下面是上述功能的实现:

**程序 1:**

```java
// Java program to implement
// the above function
import java.text.NumberFormat;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        // Get the Currency Instance
        NumberFormat nF1
            = NumberFormat
                  .getCurrencyInstance();

        // Get the Currency Instance
        NumberFormat nF2
            = NumberFormat
                  .getCurrencyInstance();

        // Check if equal or not
        if (nF1.equals(nF2))
            System.out.println("Yes both are equal");
        else
            System.out.println("Yes both are not equal");
    }
}
```

**输出:**

```java
Yes both are equal

```

**程序二:**

```java
// Java program to implement
// the above function
import java.text.NumberFormat;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        // Get the Currency Instance
        NumberFormat nF1
            = NumberFormat
                  .getCurrencyInstance();

        // Get the Instance
        NumberFormat nF2
            = NumberFormat
                  .getInstance();

        // Check if equal or not
        if (nF1.equals(nF2))
            System.out.println("Yes both are equal");
        else
            System.out.println("both are not equal");
    }
}
```

**输出:**

```java
both are not equal

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#equals(java.lang.Object))