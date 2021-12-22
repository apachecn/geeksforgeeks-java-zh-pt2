# Java 中的短比较()方法

> 原文:[https://www.geeksforgeeks.org/short-compare-method-in-java/](https://www.geeksforgeeks.org/short-compare-method-in-java/)

[短类](https://www.geeksforgeeks.org/java-lang-Short-class-java/)的 **compare()** 方法用于比较数值相等的两个原始短值。由于它是一个静态方法，因此可以在不创建任何 Short 对象的情况下使用。

**语法:**

```
public static int compare(short x, short y)
```

**参数:**该方法接受两个参数:

*   **x:** 是第一个要比较的 Short 对象。
*   **y:** 是要比较的 Short 对象。

**返回类型:**返回一个 **int** 值。它返回:

*   如果“x”等于“y”，则为 0，
*   正值“x”大于“y”，
*   负值“x”小于“y”

下面是 compare()方法在 Java 中的实现:
**示例 1:**

```
// Java code to demonstrate
// Short compare() method

class GFG {
    public static void main(String[] args)
    {

        short a = 4;

        short b = 4;

        // compare method in Short class
        int output = Short.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing 4 and 4 : 0

```

**例 2:**

```
// Java code to demonstrate
// Short compare() method

class GFG {
    public static void main(String[] args)
    {

        short a = 4;

        short b = 2;

        // compare method in Short class
        int output = Short.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing 4 and 2 : 2

```

**例 3:**

```
// Java code to demonstrate
// Short compare() method

class GFG {
    public static void main(String[] args)
    {

        short a = 2;

        short b = 4;

        // compare method in Short class
        int output = Short.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing 2 and 4 : -2

```