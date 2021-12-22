# 包装类的实用方法| valueOf()、xxxValue()、parseXxx()、toString()

> 原文:[https://www . geesforgeks . org/utility-methods-wrapper-class-value of-xxxvalue-parsexxx-tostring/](https://www.geeksforgeeks.org/utility-methods-wrapper-classes-valueof-xxxvalue-parsexxx-tostring/)

**先决条件:** [包装类](https://www.geeksforgeeks.org/wrapper-classes-java/)

**包装器类的实用方法:**包装器类的目标是定义原语类型所需的几种实用方法。包装类定义的原语类型有 4 种实用方法:

1.  **valueOf()方法:**我们可以使用 valueOf()方法为给定的原语或字符串创建 Wrapper 对象。有 3 种类型的 valueOf()方法:
    *   **包装器值 Of(字符串):**除了字符类之外，每个包装器类都包含一个静态值 Of()方法，用于为给定的字符串创建包装器类对象。
        **语法:**

        ```
        public static Wrapper valueOf(String s);
        ```

        ## Java 语言（一种计算机语言,尤用于创建网站)

        ```
        // Java program to illustrate valueof()

        class GFG {
            public static void main(String[] args)
            {
                Integer I = Integer.valueOf("10");
                System.out.println(I);
                Double D = Double.valueOf("10.0");
                System.out.println(D);
                Boolean B = Boolean.valueOf("true");
                System.out.println(B);

                // Here we will get RuntimeException
                Integer I1 = Integer.valueOf("ten");
            }
        }
        ```

        输出:

```
10
10.0
true
Exception in thread "main" java.lang.NumberFormatException: For input string: "ten"

```

*   **包装器值 Of(字符串 s，整数基数):**每个整数包装器类 Byte，Short，Integer，Long)都包含以下 valueOf()方法，为给定的具有指定基数的字符串创建包装器对象。基数的范围是 2 到 36。
    **语法:**

    ```
    public static Wrapper valueOf(String s, int radix)
    ```

    ## Java 语言（一种计算机语言,尤用于创建网站)

    ```
    // Java program to illustrate valueof()

    class GFG {
        public static void main(String[] args)
        {
            Integer I = Integer.valueOf("1111", 2);
            System.out.println(I);
            Integer I1 = Integer.valueOf("1111", 4);
            System.out.println(I1);
        }
    }
    ```

    输出:

    ```
    15
    85

    ```

    *   **Wrapper valueOf(primitive p) :** Every Wrapper class including Character class contains the following method to create a Wrapper object for the given primitive type.

    **语法:**

    ```
    public static Wrapper valueOf(primitive p);
    ```

    ## Java 语言（一种计算机语言，尤用于创建网站）

    ```
    // Java program to illustrate valueof()

    class GFG {
        public static void main(String[] args)
        {
            Integer I = Integer.valueOf(10);
            Double D = Double.valueOf(10.5);
            Character C = Character.valueOf('a');
            System.out.println(I);
            System.out.println(D);
            System.out.println(C);
        }
    }
    ```

    Output:

    ```
    10
    10.5
    a

    ```

    *   **xxxValue()方法:**我们可以使用 xxxValue()方法来获取给定包装对象的原语。每个数字类型包装器类(字节、短、整数、长、浮点、双)包含以下 6 种方法来获取给定包装器对象的原语:

    ## Java 语言（一种计算机语言,尤用于创建网站)

    ```
    // Java program to illustrate bytevalue()

    class GFG {
        public static void main(String[] args)
        {
            Integer I = new Integer(130);
            System.out.println(I.byteValue());
            System.out.println(I.shortValue());
            System.out.println(I.intValue());
            System.out.println(I.longValue());
            System.out.println(I.floatValue());
            System.out.println(I.doubleValue());
        }
    }
    ```

    输出:

    ```
    -126
    130
    130
    130
    130.0
    130.0

    ```

    1.  公共字节字节值（）
    2.  公共短值()
    3.  public intValue（）
    4.  public long longvalue()
    5.  公共浮点浮点值()
    6.  公共浮点 doubleValue()*   **parseXxx()方法:**我们可以使用 parseXxx()方法将 String 转换为原语。parseXxx()方法有两种类型:
    *   **原语 parseXxx(字符串):**除了字符类之外的每个包装类都包含以下 parseXxx()方法来为给定的字符串对象查找原语。
        **语法:**

        ```
        public static primitive parseXxx(String s);
        ```

        ## Java 语言（一种计算机语言,尤用于创建网站)

        ```
        // Java program to illustrate parseXxx()

        class GFG {
            public static void main(String[] args)
            {
                int i = Integer.parseInt("10");
                double d = Double.parseDouble("10.5");
                boolean b = Boolean.parseBoolean("true");
                System.out.println(i);
                System.out.println(d);
                System.out.println(b);
            }
        }
        ```

        输出:

```
10
10.5
true

```

*   **parseXxx(String s, int radix) :** Every Integral type Wrapper class (Byte, Short, Integer, Long) contains the following parseXxx() method to convert specified radix String to primitive.

    **语法:**

    ```
    public static primitive parseXxx(String s, int radix);
    ```

    ## Java 语言（一种计算机语言，尤用于创建网站）

    ```
    // Java program to illustrate parseXxx()

    class GFG {
        public static void main(String[] args)
        {
            int i = Integer.parseInt("1000", 2);
            long l = Long.parseLong("1111", 4);
            System.out.println(i);
            System.out.println(l);
        }
    }
    ```

    Output:

    ```
    8
    85

    ```

    *   **toString()方法:**我们可以使用 toString()方法将 Wrapper 对象或原语转换为 String。toString()方法的形式很少:

    T4】
    *   **公共字符串 toString() :** 每个包装类都包含以下 toString()方法，用于将包装对象转换为字符串类型。
        **语法:**

        ```
        public String toString();
        ```

        ## Java 语言（一种计算机语言,尤用于创建网站)

        ```
        // Java program to illustrate toString()

        class GFG {
            public static void main(String[] args)
            {
                Integer I = new Integer(10);
                String s = I.toString();
                System.out.println(s);
            }
        }
        ```

        输出:

        ```
        10

        ```

    *   **toString(原语 p) :** 包括 Character 类在内的每个 Wrapper 类都包含以下静态 toString()方法，用于将原语转换为字符串。
        **语法:**

        ```
        public static String toString(primitive p);
        ```

        ## Java 语言（一种计算机语言,尤用于创建网站)

        ```
        // Java program to illustrate toString()

        class GFG {
            public static void main(String[] args)
            {
                String s = Integer.toString(10);
                System.out.println(s);
                String s1 = Character.toString('a');
                System.out.println(s1);
            }
        }
        ```

        输出:

        ```
        10
        a

        ```

    *   **toString(primitive p, int radix) :** Integer and Long classes contains the following toString() method to convert primitive to specified radix String.

        **语法:**

        ```
        public static String toString(primitive p, int radix);
        ```

        ## Java 语言（一种计算机语言，尤用于创建网站）

        ```
        // Java program to illustrate toString()

        class GFG {
            public static void main(String[] args)
            {
                String s = Integer.toString(15, 2);
                System.out.println(s);
                String s1 = Long.toString(11110000, 4);
                System.out.println(s1);
            }
        }
        ```

        Output:

        ```
        1111
        222120121300

        ```