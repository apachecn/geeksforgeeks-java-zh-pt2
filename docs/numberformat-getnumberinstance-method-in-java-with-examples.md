# Java 中的 NumberFormat getNumberInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/number format-getnumberinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getnumberinstance-method-in-java-with-examples/)

1.  The **getNumberInstance()** method is a built-in method of the **[java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/)** returns an general purpose number format for the current default FORMAT locale.

    **语法**:

    > 公共静态最终数字格式 getNumberInstance()

    **参数**:该功能不接受任何参数。

    **返回值**:该函数返回通用格式的 NumberFormat 实例。

    下面是上述功能的实现:

    **程序 1:**

    ```java
    // Java program to implement
    // the above function

    import java.text.NumberFormat;
    import java.util.Locale;
    import java.util.Currency;

    public class Main {
        public static void main(String[] args)
            throws Exception
        {

            // Get the number instance
            NumberFormat nF
                = NumberFormat
                      .getNumberInstance();

            // Sets the currency to Canadian Dollar
            nF.setCurrency(
                Currency.getInstance(
                    Locale.CANADA));

            // Stores the values
            String values
                = nF.getCurrency().getDisplayName();

            // Prints the currency
            System.out.println(values);
        }
    }
    ```

    **Output:**

    ```java
    Canadian Dollar

    ```

    **程序 2:**

    ```java
    // Java program to implement
    // the above function

    import java.text.NumberFormat;
    import java.util.Locale;
    import java.util.Currency;

    public class Main {
        public static void main(String[] args)
            throws Exception
        {

            // Get the number instance
            NumberFormat nF
                = NumberFormat
                      .getNumberInstance();

            // Stores the values
            String values
                = nF.getCurrency()
                      .getDisplayName();

            // Prints the currency
            System.out.println(values);
        }
    }
    ```

    **Output:**

    ```java
    US Dollar

    ```

    **参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # getNumberInstance()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getNumberInstance())

2.  The **getNumberInstance(Locale inLocale)** method is a built-in method of the **[java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/)** returns a general-purpose number format for any specified locale.

    **语法**:

    > public static number format getnumberstance(本地内置)

    **参数**:该函数在 Locale 中接受单个强制参数**，该参数描述要指定的区域设置。**

    **返回值**:该函数返回通用数字格式的数字格式实例。

    下面是上述功能的实现:

    **程序 1:**

    ```java
    // Java program to implement
    // the above function

    import java.text.NumberFormat;
    import java.util.Locale;
    import java.util.Currency;

    public class Main {
        public static void main(String[] args)
            throws Exception
        {

            // Get the integer instance
            NumberFormat nF
                = NumberFormat.getNumberInstance(
                    Locale.CANADA);

            // Stores the values
            String values
                = nF.getCurrency()
                      .getDisplayName();

            // Prints the currency
            System.out.println(values);
        }
    }
    ```

    **Output:**

    ```java
    Canadian Dollar

    ```

    **参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # getNumberInstance(Java . util . locale)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getNumberInstance(java.util.Locale))