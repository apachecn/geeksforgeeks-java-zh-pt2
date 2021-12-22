# Java 中的 ZonedDateTime getLong()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-getlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-getlong-method-in-java-with-examples/)

Java 中 **ZonedDateTime** 类的 **getLong()** 方法用于从这个 ZonedDateTime 中获取作为输入传递的指定字段的值作为长值。此方法向此区域数据时间查询字段值，返回值将始终在字段值的有效范围内。当字段不受支持并且方法无法返回 int 值时，将引发异常。

**语法:**

```
public int getLong(TemporalField field)

```

**参数:**该方法接受单个参数**字段**，代表要获取的字段。这是一个强制参数，不应为空。

**返回值:**该方法为该字段返回一个 **int** 值。

**异常:**该方法抛出以下异常:

*   **日期时间异常**:如果无法获取字段的值或者该值超出了字段有效值的范围。
*   **unsupportedtemporaltypexception**:如果不支持该字段或者值的范围超过了一个整数。
*   **算术异常**:如果出现数值溢出。

下面的程序说明了 getLong()方法:
**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.getLong() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDT
            = ZonedDateTime.parse("2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get all enum of chronofield
        // and iterate through all enum values
        for (ChronoField field : ChronoField.values()) {

            try {
                // get long value of field
                long value = zonedDT.getLong(field);
                System.out.println("field : " + field
                                   + " || value : " + value);
            }
            catch (Exception e) {
                System.out.println("e " + field);
            }
        }
    }
}
```

**Output:**

```
field : NanoOfSecond || value : 123000000
field : NanoOfDay || value : 69672123000000
field : MicroOfSecond || value : 123000
field : MicroOfDay || value : 69672123000
field : MilliOfSecond || value : 123
field : MilliOfDay || value : 69672123
field : SecondOfMinute || value : 12
field : SecondOfDay || value : 69672
field : MinuteOfHour || value : 21
field : MinuteOfDay || value : 1161
field : HourOfAmPm || value : 7
field : ClockHourOfAmPm || value : 7
field : HourOfDay || value : 19
field : ClockHourOfDay || value : 19
field : AmPmOfDay || value : 1
field : DayOfWeek || value : 4
field : AlignedDayOfWeekInMonth || value : 6
field : AlignedDayOfWeekInYear || value : 4
field : DayOfMonth || value : 6
field : DayOfYear || value : 340
field : EpochDay || value : 17871
field : AlignedWeekOfMonth || value : 1
field : AlignedWeekOfYear || value : 49
field : MonthOfYear || value : 12
field : ProlepticMonth || value : 24227
field : YearOfEra || value : 2018
field : Year || value : 2018
field : Era || value : 1
field : InstantSeconds || value : 1544104272
field : OffsetSeconds || value : 19800

```

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.getLong() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDT
            = ZonedDateTime.parse("2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // try to find AMPM_OF_DAY
        // using ChronoField.AMPM_OF_DAY
        // in getLong method
        try {

            long value
                = zonedDT.getLong(
                    ChronoField.AMPM_OF_DAY);

            // print result
            System.out.println("AMPM_OF_DAY value: " + value);
        }
        catch (Exception e) {

            // print exception
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
AMPM_OF_DAY value: 1

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # getLong(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#getLong(java.time.temporal.TemporalField))