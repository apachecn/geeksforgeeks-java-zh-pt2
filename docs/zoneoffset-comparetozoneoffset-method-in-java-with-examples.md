# 区域偏移比较 Java 中的(区域偏移)方法，示例

> 原文:[https://www . geeksforgeeks . org/zone offset-comparetozone offset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-comparetozoneoffset-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的 **compareTo(ZoneOffset)** 方法用于比较作为参数传递给该 ZoneOffset 实例的 ZoneOffset 的另一个实例。此方法返回一个整数值，即比较器值。

**语法:**

```java
public int compareTo(ZoneOffset anotherZoneOffset)

```

**参数:**该方法接受一个参数**另一个区域偏移**，该参数将与该区域偏移实例进行比较。

**返回值:**该方法返回一个**整数值**，如下所示:

*   如果此实例大于作为参数传递的实例，则返回正值
*   如果此实例等于作为参数传递的实例，则返回零(0)
*   if this instance is less than instance passed as a parameter then a negative value is returned.

    **异常:**如果作为参数传递的另一个区域偏移量为空，此方法将引发**空指针异常**。

    以下示例说明了 ZoneOffset.compareTo()方法:

    **例 1:**

    ```java
    // Java code to illustrate compareTo() method

    import java.time.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Get the ZoneOffset instance
            ZoneOffset zoneOffset1
                = ZoneOffset.ofHours(5);
            System.out.println("ZoneOffset 1: "
                               + zoneOffset1);

            // Get the ZoneOffset instance
            ZoneOffset zoneOffset2
                = ZoneOffset.ofHours(5);
            System.out.println("ZoneOffset 2: "
                               + zoneOffset2);

            // Get the ZoneOffset instance
            ZoneOffset zoneOffset3
                = ZoneOffset.ofHours(3);
            System.out.println("ZoneOffset 3: "
                               + zoneOffset3);

            // Using compareTo() method
            System.out.println("ZoneOffset 1 "
                               + "compared to ZoneOffset 2: "
                               + zoneOffset1.compareTo(zoneOffset2));

            // Using compareTo() method
            System.out.println("ZoneOffset 1 "
                               + "compared to ZoneOffset 3: "
                               + zoneOffset1.compareTo(zoneOffset3));

            // Using compareTo() method
            System.out.println("ZoneOffset 3 "
                               + "compared to ZoneOffset 1: "
                               + zoneOffset3.compareTo(zoneOffset1));
        }
    }
    ```

    **Output:**

    ```java
    ZoneOffset 1: +05:00
    ZoneOffset 2: +05:00
    ZoneOffset 3: +03:00
    ZoneOffset 1 compared to ZoneOffset 2: 0
    ZoneOffset 1 compared to ZoneOffset 3: -7200
    ZoneOffset 3 compared to ZoneOffset 1: 7200

    ```

    **示例 2:** 显示空指针异常

    ```java
    // Java code to illustrate compareTo() method

    import java.time.*;

    public class GFG {
        public static void main(String[] args)
        {

            try {
                // Get the ZoneOffset instance
                ZoneOffset zoneOffset
                    = ZoneOffset.ofHours(3);
                System.out.println("ZoneOffset: "
                                   + zoneOffset);

                // Using compareTo() method
                System.out.println("ZoneOffset "
                                   + "compared to null: ");

                zoneOffset.compareTo(null);
            }
            catch (Exception e) {
                System.out.println(e);
            }
        }
    }
    ```

    **Output:**

    ```java
    ZoneOffset: +03:00
    ZoneOffset compared to null: 
    java.lang.NullPointerException

    ```

    **参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#compareTo-java.time.ZoneOffset-)