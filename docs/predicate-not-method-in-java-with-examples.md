# Java 中的谓词. not()方法，示例

> 原文:[https://www . geesforgeks . org/predicate-not-method-in-Java-with-examples/](https://www.geeksforgeeks.org/predicate-not-method-in-java-with-examples/)

为了否定现有的谓词，在 Java 11 中添加了谓词. not()静态方法。谓词类存在于 java.util.function 包中。

**语法:**

```
negate = Predicate.not( positivePredicate );
```

**参数:**

*   需要否定的谓词

**返回类型:**返回类型非()方法为谓词。

**进场:**

1.  创建一个谓词并初始化它的条件。
2.  创建另一个谓词来创建否定，并使用 not()方法分配它。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Implementation of Predicate.not() method in Java
import java.util.Arrays;
import java.util.List;
import java.util.function.Predicate;
import java.util.stream.Collectors;

public class GFG {
    public static void main(String[] args)
    {
        List<Integer> list
            = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // creating a predicate for negation
        Predicate<Integer> even = i -> i % 2 == 0;

        // creating a predicate object which
        // is negation os supplied predicate
        Predicate<Integer> odd = Predicate.not(even);

        // filtering the even number using even predicate
        List<Integer> evenNumbers
            = list.stream().filter(even).collect(
                Collectors.toList());

        // filtering the odd number using odd predicate
        List<Integer> oddNumbers
            = list.stream().filter(odd).collect(
                Collectors.toList());
        // Print the Lists
        System.out.println(evenNumbers);
        System.out.println(oddNumbers);
    }
}
```

**输出:**

```
[2, 4, 6, 8, 10]
[1, 3, 5, 7, 9]
```