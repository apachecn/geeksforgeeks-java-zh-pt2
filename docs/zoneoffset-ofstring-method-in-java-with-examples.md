# Java 中(字符串)方法的区域偏移量，示例

> 原文:[https://www . geesforgeks . org/zone offset-of string-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-ofstring-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的(字符串)方法的**用于使用作为参数传递的 offsetId 获取 ZoneOffset 的实例。该方法以字符串的形式将偏移量作为参数，并将其转换为区域偏移量。返回的偏移量的 ID 将被规范化为 getId()描述的格式之一。
该方法接受的字符串偏移量列表如下:**

*   z–世界协调时
*   +h
*   +hh
*   +hh:mm
*   -嗯
*   +hhmm
*   -hhmm
*   +hh:mm:ss
*   -hh:mm:ss
*   +hhmmss
*   -hhmmss

    **注:**表示加号或减号。支持的最大范围为+18:00 到-18:00(含)。

    **语法:**

    ```java
    public static ZoneOffset of(String offsetId)

    ```

    **参数:**该方法接受一个参数 **offsetId** ，该参数是要解析为 ZoneOffset 实例的字符串。

    **返回值:**这个方法返回一个从指定偏移量解析的**区域偏移量实例**。

    **异常:**如果偏移标识无效，该方法抛出**日期时间异常**。

    以下示例说明了 ZoneOffset.of()方法:

    **例 1:**

    ```java
    // Java code to illustrate of() method

    import java.time.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Get the offset ID
            String offsetId = "Z";

            // ZoneOffset using of() method
            ZoneOffset zoneOffset
                = ZoneOffset.of(offsetId);

            System.out.println(zoneOffset);
        }
    }
    ```

    **Output:**

    ```java
    Z

    ```

    **示例 2:** 演示日期时间异常

    ```java
    // Java code to illustrate of() method

    import java.time.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Get the invalid offset ID
            String offsetId = "10:10";

            try {
                // ZoneOffset using of() method
                ZoneOffset zoneOffset
                    = ZoneOffset.of(offsetId);
            }

            catch (Exception e) {
                System.out.println(e);
            }
        }
    }
    ```

    **Output:**

    ```java
    java.time.DateTimeException: Invalid ID for ZoneOffset, non numeric characters found: 10:10

    ```

    **参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#of-java.lang.String-)