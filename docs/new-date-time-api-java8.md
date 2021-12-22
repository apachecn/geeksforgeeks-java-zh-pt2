# Java 8 中新的日期时间 API

> 原文:[https://www.geeksforgeeks.org/new-date-time-api-java8/](https://www.geeksforgeeks.org/new-date-time-api-java8/)

Java 8 中引入了新的日期时间 API，以克服旧的日期时间 API 的以下缺点:

1.  **【 unsafe thread:** Unlike the old java.util.Date of unsafe thread, the new date-time API is *immutable* and has no setter method.
2.  **Less operations:** There are only a few date operations in the old API, but the new API provides us with many date operations.

Java 8 在 java.time 包下引入了一个新的日期时间 API，其中最重要的类是:

1.  **Local:** Simplified date and time API without the complexity of time zone processing.
2.  **Partition:** Special date and time API, which handles various time zones.

*   **当地日期/地点时间** **当地日期时间 API:** 不需要时区时使用。

## Java

```
// Java code for LocalDate
// / LocalTime Function
import java.time.*;
import java.time.format.DateTimeFormatter;

public class Date {

public static void LocalDateTimeApi()
{

    // the current date
    LocalDate date = LocalDate.now();
    System.out.println("the current date is "+
                        date);

    // the current time
    LocalTime time = LocalTime.now();
    System.out.println("the current time is "+
                        time);

    // will give us the current time and date
    LocalDateTime current = LocalDateTime.now();
    System.out.println("current date and time : "+
                        current);

    // to print in a particular format
    DateTimeFormatter format =
      DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm:ss"); 

    String formatedDateTime = current.format(format); 

    System.out.println("in formatted manner "+
                        formatedDateTime);

    // printing months days and seconds
    Month month = current.getMonth();
    int day = current.getDayOfMonth();
    int seconds = current.getSecond();
    System.out.println("Month : "+month+" day : "+
                        day+" seconds : "+seconds);

    // printing some specified date
    LocalDate date2 = LocalDate.of(1950,1,26);
    System.out.println("the republic day :"+date2);

    // printing date with current time.
    LocalDateTime specificDate =
        current.withDayOfMonth(24).withYear(2016);

    System.out.println("specific date with "+
                       "current time : "+specificDate);
}

    // Driver code
    public static void main(String[] args)
    {
        LocalDateTimeApi();
    }
}
```

**输出**

```
the current date is 2021-09-23
the current time is 20:52:39.954238
current date and time : 2021-09-23T20:52:39.956909
in formatted manner 23-09-2021 20:52:39
Month : SEPTEMBER day : 23 seconds : 39
the republic day :1950-01-26
specific date with current time : 2016-09-24T20:52:39.956909

```

*   **partition date and time API** : the time zone is considered as

## Java

```
// Java code for Zoned date-time API
import java.time.LocalDateTime;
import java.time.ZoneId;
import java.time.ZonedDateTime;
import java.time.format.DateTimeFormatter;

public class Zone {

// Function to get Zoned Date and Time
public static void ZonedTimeAndDate()
{
    LocalDateTime date = LocalDateTime.now();
    DateTimeFormatter format1 =
      DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm:ss");

    String formattedCurrentDate = date.format(format1);

    System.out.println("formatted current Date and"+
                      " Time : "+formattedCurrentDate);

    // to get the current zone
    ZonedDateTime currentZone = ZonedDateTime.now();
    System.out.println("the current zone is "+
                        currentZone.getZone());

    // getting time zone of specific place
    // we use withZoneSameInstant(): it is
    // used to return a copy of this date-time
    // with a different time-zone, 
    // retaining the instant.
    ZoneId tokyo = ZoneId.of("Asia/Tokyo");

    ZonedDateTime tokyoZone =
            currentZone.withZoneSameInstant(tokyo);

    System.out.println("tokyo time zone is " +
                        tokyoZone);

    DateTimeFormatter format =
        DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm:ss");

    String formatedDateTime = tokyoZone.format(format);

    System.out.println("formatted tokyo time zone "+
                        formatedDateTime);

}

    // Driver code
    public static void main(String[] args)
    {

        ZonedTimeAndDate();

    }
}
```

**输出:**

```
formatted current Date and Time : 09-04-2018 06:21:13
the current zone is Etc/UTC
tokyo time zone is 2018-04-09T15:21:13.220+09:00[Asia/Tokyo]
formatted tokyo time zone 09-04-2018 15:21:13
```