# Java 中的 NumberFormat getIntegerInstance()方法，带示例

> 原文:[https://www . geeksforgeeks . org/number format-getintegerinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getintegerinstance-method-in-java-with-examples/)

1.  The **getIntegerInstance()** method is a built-in method of the **[java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/)** returns an integer number format for the current default FORMAT locale.

    **语法**:

    ```
    public static final NumberFormat getIntegerInstance()
    ```

    **参数**:该功能不接受任何参数。

    **返回值**:该函数返回整型值通用格式的 NumberFormat 实例。

    下面是上述功能的实现:

    **程序 1:**

    ```
    // Java program to implement
    // the above function
    import java.text.NumberFormat;
    import java.util.Locale;
    import java.util.Currency;
    public class Main {
        public static void main(String[] args) throws Exception
        {

            // Get the integer instance
            NumberFormat nF = NumberFormat.getIntegerInstance();

            // Sets the currency to Canadian Dollar
            nF.setCurrency(Currency.getInstance(Locale.CANADA));

            // Stores the values
            String values = nF.getCurrency().getDisplayName();

            // Prints the currency
            System.out.println(values);
        }
    }
    ```

    **Output:**

    ```
    Canadian Dollar

    ```

    **程序 2:**

    ```
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
                = NumberFormat
                      .getIntegerInstance();

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

    ```
    US Dollar

    ```

    **参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/number format . html # getIntegerInstance()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getIntegerInstance())

2.  The **getIntegerIntegerInstance(Locale inLocale)** method is a built-in method of the **[java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/)** returns a integer number format for any specified locale.

    **语法**:

    > public static number format getintentangenstance(局部内孔)

    **参数**:该函数在 Locale 中接受单个强制参数**，该参数描述要指定的区域设置。**

    **返回值**:该函数返回整数值的整数格式实例。

    下面是上述功能的实现:

    **程序 1:**

    ```
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
                = NumberFormat
                      .getIntegerInstance(
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

    ```
    Canadian Dollar

    ```

    **参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/text/number format . html # getintenstance(Java . util . locale)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getIntegerInstance(java.util.Locale))