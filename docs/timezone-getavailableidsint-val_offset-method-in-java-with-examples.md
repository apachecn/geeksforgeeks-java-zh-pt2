# Java 中的 time zone getAvailableIDs(int val _ offset)方法，示例

> 原文:[https://www . geesforgeks . org/time zone-getavailableidsint-val _ offset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-getavailableidsint-val_offset-method-in-java-with-examples/)

Java 中 **TimeZone 类**的**getavailable IDs(int*val _ offset*)**方法用于根据提供的 offset 值获取 TimeZone 类中所有支持的可用 id 列表。

**语法:**

> 公共静态字符串[]getAvailableIDs(int*val _ offset*)

**参数:**该方法取*整数*类型的一个参数 **val_offset** ，该参数是指时区偏移值..

**返回值:**该方法返回所有可用标识的**数组**，其中该标识的时区具有指定值。

下面的程序说明了时区的 getAvailableIDs()方法的工作原理:

**例 1:**

```java
// Java code to illustrate
// getAvailableIDs() method

import java.util.*;

public class TimeZone_Demo {
    public static void main(String args[])
    {

        // Storing all the available Ids
        String[] Id_array
            = TimeZone.getAvailableIDs(7200000);

        // Displaying all the available Ids
        System.out.println("All the available"
                           + " Ids are: ");

        for (int count = 0;
             count < Id_array.length;
             count++)
            System.out.println(Id_array[count]);
    }
}
```

**输出:**

```java
All the available Ids are: 
ART
Africa/Blantyre
Africa/Bujumbura
Africa/Cairo
Africa/Gaborone
Africa/Harare
Africa/Johannesburg
Africa/Khartoum
Africa/Kigali
Africa/Lubumbashi
Africa/Lusaka
Africa/Maputo
Africa/Maseru
Africa/Mbabane
Africa/Tripoli
Africa/Windhoek
Asia/Amman
Asia/Beirut
Asia/Damascus
Asia/Famagusta
Asia/Gaza
Asia/Hebron
Asia/Jerusalem
Asia/Nicosia
Asia/Tel_Aviv
CAT
EET
Egypt
Etc/GMT-2
Europe/Athens
Europe/Bucharest
Europe/Chisinau
Europe/Helsinki
Europe/Kaliningrad
Europe/Kiev
Europe/Mariehamn
Europe/Nicosia
Europe/Riga
Europe/Sofia
Europe/Tallinn
Europe/Tiraspol
Europe/Uzhgorod
Europe/Vilnius
Europe/Zaporozhye
Israel
Libya

```

**例 2:**

```java
// Java code to illustrate
// getAvailableIDs() method

import java.util.*;

public class TimeZone_Demo {
    public static void main(String args[])
    {

        // Storing all the available Ids
        String[] Id_array
            = TimeZone.getAvailableIDs(36000000);

        // Displaying all the available Ids
        System.out.println("All the available"
                           + " Ids are: ");

        for (int count = 0;
             count < Id_array.length;
             count++)
            System.out.println(Id_array[count]);
    }
}
```

**输出:**

```java
All the available Ids are: 
AET
Antarctica/DumontDUrville
Asia/Ust-Nera
Asia/Vladivostok
Australia/ACT
Australia/Brisbane
Australia/Canberra
Australia/Currie
Australia/Hobart
Australia/Lindeman
Australia/Melbourne
Australia/NSW
Australia/Queensland
Australia/Sydney
Australia/Tasmania
Australia/Victoria
Etc/GMT-10
Pacific/Chuuk
Pacific/Guam
Pacific/Port_Moresby
Pacific/Saipan
Pacific/Truk
Pacific/Yap

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # getAvailableIDs(int)](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#getAvailableIDs(int))