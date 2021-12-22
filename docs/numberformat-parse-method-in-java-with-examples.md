# Java 中的 NumberFormat 解析()方法，示例

> 原文:[https://www . geesforgeks . org/number format-parse-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-parse-method-in-java-with-examples/)

1.  The **parse(str)** method is a built-in method of the [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) which parses text from the beginning of the given string to produce a number. The method may not use the entire text of the given string

    **语法:**

    ```
    public Number parse?(String str)
    ```

    **参数**:函数接受一个字符串**字符串**，其开头应该被解析。

    **返回值**:该函数返回一个从字符串中解析出来的数字。

    **异常**:如果指定字符串的开头无法解析，函数会抛出**解析异常**。

    下面是上述功能的实现:

    **程序 1** :

    ```
    // Java program to implement
    // the above function

    import java.text.NumberFormat;
    import java.util.Locale;
    import java.text.ParsePosition;

    public class Main {
        public static void main(String[] args)
            throws Exception
        {

            // Get the number instance
            NumberFormat nF
                = NumberFormat.getNumberInstance();

            // Prints the parsed number or NULL
            System.out.println("Number parsed: "
                               + nF.parse("567"));
        }
    }
    ```

    **Output:**

    ```
    Number parsed: 567

    ```

2.  The **parse(str, parseIndex)** method is a built-in method of the [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) which parses a number from the text and returns a Long if possible, otherwise a Double. If IntegerOnly is set, will stop at a decimal point (or equivalent; e.g., for rational numbers “1 2/3”, will stop after the 1).

    **语法:**

    > 公共抽象数字解析(字符串，解析位置解析索引)

    **参数**:该功能接受两个参数，描述如下:

    *   **str:** specifies the string to be parsed.

        **解析索引:**指定解析位置

    **返回值**:该函数返回一个从字符串中解析出来的数字。

    下面是上述功能的实现:

    **程序 1** :

    ```
    // Java program to implement
    // the above function

    import java.text.NumberFormat;
    import java.util.Locale;
    import java.text.ParsePosition;

    public class Main {
        public static void main(String[] args)
            throws Exception
        {

            // Get the number instance
            NumberFormat nF
                = NumberFormat.getNumberInstance();

            // Prints the parsed number or NULL
            System.out.println("Number parsed: "
                               + nF.parse("567",
                                          new ParsePosition(1)));
        }
    }
    ```

    **Output:**

    ```
    Number parsed: 67

    ```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # parse(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#parse(java.lang.String))