# Java 中的 NumberFormat getPercentInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/number format-getpercentinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getpercentinstance-method-in-java-with-examples/)

1.  The **getPercentInstance()** method is a built-in method of the **[java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/)** returns a percentage format for the current default FORMAT locale.

    **语法**:

    > 公共静态最终数字格式 getPercentInstance()

    **参数**:该功能不接受任何参数。

    **返回值**:该函数返回百分比格式的数字格式实例。

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

            // Get the percent instance
            NumberFormat nF
                = NumberFormat.getPercentInstance();

            // Sets the currency to Canadian Dollar
            nF.setCurrency(Currency
                               .getInstance(
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

            // Get the percent instance
            NumberFormat nF
                = NumberFormat
                      .getPercentInstance();

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

    **参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # getPercentInstance()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getPercentInstance())

2.  The **getPercentInstance(Locale inLocale)** method is a built-in method of the **[java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/)** returns a percentage format for any specified locale.

    **语法**:

    > public static number format get ercentance(本地内置)

    **参数**:该函数在 Locale 中接受单个强制参数**，该参数描述要指定的区域设置。**

    **返回值**:该函数返回百分比格式的数字格式实例。

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

            // Get the percent instance
            NumberFormat nF
                = NumberFormat
                      .getPercentInstance(
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

    **参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/text/number format . html # get ercentance(Java . util . locale)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getPercentInstance(java.util.Locale))