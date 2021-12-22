# 用 java 的公历打印一周中的某一天

> 原文:[https://www . geesforgeks . org/print-一周中的某一天使用 java 中的公历/](https://www.geeksforgeeks.org/print-day-of-week-using-gregorian-calendar-in-java/)

给定一个日期，你必须打印一周中的某一天。

示例:

```
Input : 2018 3 26
Output : Mon

Input : 2010 8 9
Output : Wed

```

想法是使用 java 内置 API **公历**。
公历日历是日历的一个具体子类，提供了世界上大多数国家使用的标准日历系统
。
公历日期(年、月、日)构造一个
公历日期，给定日期设置在默认时区
默认区域设置。
创建几个条件来检查
输入数据的有效性。如果发现输入错误，将输出**无效的**
信息。

```
// Necessary imports for using Gregorian Calendar
import java.util.Calendar;
import java.util.GregorianCalendar;

class GFG {
    static int method(int year, int month, int day)
    {
        // to check the validity of day of month
        int[] darr = { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };

        // check validity of year and month
        if (year > 0 && (month > 0 && month <= 12)) {

            // check for a leap year and month of February

            if ((year % 4 == 0 || year % 400 == 0) && 
                month == 2 && (day > 0 && day <= 29)) {

                // month starts at zero, so we need to put ( month - 1 ).
                Calendar calendar = new GregorianCalendar(year, month - 1, day);
                return calendar.get(Calendar.DAY_OF_WEEK);
            }
            else {

                // check the range of day of month
                if (day > 0 && day <= darr[month - 1]) {

                    // month starts at zero, so we need to put ( month - 1 ).
                    Calendar calendar = new GregorianCalendar(year, month - 1, day);
                    return calendar.get(Calendar.DAY_OF_WEEK);
                }
                else
                    return 0;
            }
        }
        else
            return 0;
    }
    public static void main(String[] args)
    {
        String[] dayofweek = { "Invalid", "Sun", "Mon", "Tue",
                                "Wed", "Thur", "Fri", "Sat" };
        int y = 2018, m = 3, d = 26;
        System.out.println(dayofweek[method(y, m, d)]);
    }
}
```

**Output:**

```
Mon

```