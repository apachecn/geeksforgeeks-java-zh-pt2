# Java 中的@SuppressWarnings 注释

> 原文:[https://www . geesforgeks . org/the-suppress warnings-annotation-in-Java/](https://www.geeksforgeeks.org/the-suppresswarnings-annotation-in-java/)

注释是现代技术中 Java 的一个非常重要的部分，大多数技术，如 Hibernate、Spring、Spring Boot、JPA 等等，都在使用注释，这让开发人员的生活变得非常轻松。在 Java 中，内置的通用注释是–

1.  @覆盖
2.  @已弃用
3.  @ FunctionalInterface
4.  **@抑制警告**

**语法:【Java @ SuppressWarnings 注释的签名如下:**

```java
@Retention(value=SOURCE)
@Target(value = {TYPE, FIELD, METHOD, PARAMETER, CONSTRUCTOR, LOCAL_VARIABLE })
public @interface SuppressWarnings {
       String[] value;
    }
```

我们可以看到，上面的签名只有一个元素，即字符串数组，有多个可能的值。

所有注释都有两个属性:

1.  **Target**(@ Target(value = { TYPE，FIELD，METHOD，PARAMETER，CONSTRUCTOR，LOCAL _ VARIABLE })–它将用于几乎所有内容，无论您想要隐藏警告的位置。
2.  **保留** (@Retention(value=SOURCE)):函数接口“SOURCE”的保留策略，意思是注释要到编译器才会走。

**插图:**

使用@SuppressWarnings 是为了抑制或忽略来自编译器的警告，也就是说，编译器将忽略该段代码的警告(如果有的话)。

```java
1\. @SuppressWarnings("unchecked")
   public class Calculator {
          }

- Here, it will ignore all unchecked warnings coming from that class. (All methods, variables, constructors).
```

```java
2\. public class Calculator {
   @SuppressWarnings("unchecked")
      public int sum(x,y) {
        .
      }
   }

- It will stop warning from that function only, and not from other functions of Calculator class.
```

这个注释是危险的，因为警告是代码中潜在的错误。因此，如果我们收到任何警告，第一个方法应该是解决这些错误。但是，如果我们压制任何警告，我们必须有一些坚实的理由。每次使用注释时，应在注释附近注释原因。

@SuppressWarnings 内部可能的值注释元素如下:

<figure class="table">

| 

#### value

 | describe |
| --- | --- |
| all | It will suppress all warnings. |
| coercion | Warning, while casting from generic type to unqualified type, and vice versa. |
| abandon | Ignore when we use obsolete (no longer important) methods or types. |
| div(消歧义) | Suppress division by zero warning. |
| empty | Ignore warnings of empty body statements. |
| Unchecked | It does not check whether the data type is Object or primitive. |
| fail to check | The missing statement on the switch is usually ignored (if "break" is missing). |
| hide | It suppresses relative to hidden variables. |
| 连续的 | Warning of local variable of, which causes the compiler to close a missing serialVersionUID. |
| finally | Warnings with respect to the last block that is not returned are avoided. |
| Unused | Suppress warnings relative to unused code. |

</figure>

> **注意:**使用@SuppressWarnings Annotation 的主要和最重要的好处是，如果我们因为一些已知的警告而停滞不前，那么这将忽略警告并继续前进。例如–d*发出了*警告，而*未发出*警告。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate Use of @SuppressWarnings
// Annotation

// Importing required packages
import java.io.*;
import java.lang.*;
import java.util.*;

// Class 1
// Helper class
class Addition {

    // Method 1
    public static int sum(int n1, int n2)
    {

        // Return the final sum
        return n1 + n2;
    }

    // Method 2
    public static int sum(int... nums)
    {
        int sum = 0;
        for (int i : nums) {
            sum += i;
        }

        // Return the final sum
        return sum;
    }
}

// Class 2
// Main class
// To test suppress warnings
public class GFG {

    // Does not check if data type is Object or primitive
    @SuppressWarnings("unchecked")

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of above class in main()
        // method
        Addition add = new Addition();

        // Ignore when we're using a deprecated
        // (no longer important) method or type
        @SuppressWarnings("deprecation")

        int sum = Addition.sum(10, 20);

        // Print and display the sum
        System.out.println("Sum of 10 and 20 : " + sum);

        @SuppressWarnings("rawtypes")

        // Raw data type being used instead of generic
        List list = new ArrayList();

        // Custom input entries
        list.add(12);
        list.add(120);

        // Print and display List elements
        System.out.println("List items : " + list);
    }
}
```

**Output**

```java
Sum of 10 and 20 : 30
List items : [12, 120]
```