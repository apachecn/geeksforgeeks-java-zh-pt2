# 可选类| isPresent()功能

> 原文:[https://www . geesforgeks . org/optional-class-is present-function/](https://www.geeksforgeeks.org/optional-class-ispresent-function/)

[可选类](https://www.geeksforgeeks.org/java-8-optional-class/)中的 isPresent()函数用于评估是否存在赋值给变量的值。

**语法**

```java
value.isPresent()
Returns:
It returns true if value is assigned otherwise false 

```

示例:

```java
Input : Optional value1 = Optional.ofNullable(10);
        value1.isPresent()
Output : True

Input : Optional value2 = Optional.ofNullable(null);
        value2.isPresent()
Output : False

```

```java
// Write Java code here
import java.util.Optional;
public class present {
public static void main(String args[]) {

    // Optional.ofNullable - allows passed
    // parameter to be not null.
    Optional<Integer> value1 = Optional.ofNullable(10);

    // Optional.ofNullable - allows passed
    // parameter to be null.
    Optional<Integer> value2 = Optional.ofNullable(null);
    System.out.println("First parameter is present:" +
                        value1.isPresent());
    System.out.println("Second parameter is present:" +
                        value2.isPresent());
}
}
```

```java
Output : true
Output : false

```