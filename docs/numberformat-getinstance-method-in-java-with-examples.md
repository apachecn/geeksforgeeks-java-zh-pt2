# Java 中 NumberFormat getInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/number format-getinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getinstance-method-in-java-with-examples/)

1.  The **getInstance()** method is a built-in method of the **[java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/)** returns a number format for the current default FORMAT locale.

    **语法**:

    > 公共静态最终数字格式 getInstance()

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

            // Get the instance
            NumberFormat nF
                = NumberFormat.getInstance();

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

            // Get the instance
            NumberFormat nF
                = NumberFormat.getInstance();

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
    US Dollar

    ```

    **参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/number format . html # getInstance()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getInstance())

2.  The **getInstance(Locale inLocale)** method is a built-in method of the **[java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/)** returns a number format for any specifies locale.

    **语法**:

    > public static number format getintentangenstance(局部内孔)

    **参数**:该函数接受一个描述要指定的语言环境的强制参数**。**

    **返回值**:该函数返回整数值的数字格式实例。

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
                = NumberFormat.getInstance(
                    Locale.CANADA);

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

    **参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/text/number format . html # getintenstance(Java . util . locale)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getIntegerInstance(java.util.Locale))