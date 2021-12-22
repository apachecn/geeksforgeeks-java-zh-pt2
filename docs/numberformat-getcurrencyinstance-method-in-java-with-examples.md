# Java 中 number format getcurrency instance()方法，带示例

> 原文:[https://www . geesforgeks . org/number format-getcurrency instance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getcurrencyinstance-method-in-java-with-examples/)

1.  The **getCurrencyInstance()** method is a built-in method of the **[java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/)** returns a currency format for the current default FORMAT locale.

    **语法**:

    ```java
    public static final NumberFormat getCurrencyInstance()
    ```

    **参数**:该功能不接受任何参数。

    **返回值**:该函数返回货币格式的 NumberFormat 实例

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

            // Get the currency instance
            NumberFormat nF
                = NumberFormat
                      .getCurrencyInstance();

            // Sets the currency to Canadian Dollar
            nF.setCurrency(
                Currency.getInstance(
                    Locale.CANADA));

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

            // Get the currency instance
            NumberFormat nF
                = NumberFormat
                      .getCurrencyInstance();

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

    **参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/text/number format . html # get current instance()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getCurrencyInstance())

2.  The **getCurrencyInstance(Locale inLocale)** method is a built-in method of the **[java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/)** returns a currency format for any specifies locale.

    **语法**:

    ```java
    public static NumberFormat getCurrencyInstance?(Locale inLocale)
    ```

    **参数**:该函数接受一个描述要指定的语言环境的强制参数**。**

    **返回值**:该函数返回货币格式的 NumberFormat 实例。

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

            // Get the instance
            NumberFormat nF
                = NumberFormat
                      .getCurrencyInstance(
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

    **参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/text/number format . html # get current instance(Java . util . locale)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getCurrencyInstance(java.util.Locale))