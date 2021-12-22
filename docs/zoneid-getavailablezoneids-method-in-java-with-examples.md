# Java 中的 ZoneId getAvailableZoneIds()方法，带示例

> 原文:[https://www . geesforgeks . org/zoneid-getavailablezoneids-Java 中的方法-示例/](https://www.geeksforgeeks.org/zoneid-getavailablezoneids-method-in-java-with-examples/)

**区域标识**类的 **getAvailableZoneIds()** 方法用于获取一组可用的区域标识。该集合包括所有可用的基于区域的标识。该标识可以传递给(字符串)的，以创建一个区域标识。尽管在典型的应用程序中，区域标识集是固定的，但它会随着时间的推移而增加。

**语法:**

```
public static Set getAvailableZoneIds()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回**集合**，该集合是区域标识集合的可修改副本。

下面的程序说明了 getAvailableZoneIds()方法:
**程序 1:**

```
// Java program to demonstrate
// ZoneId.getAvailableZoneIds() method

import java.time.*;
import java.util.Set;

public class GFG {
    public static void main(String[] args)
    {

        // get available zones using zoneIds()
        Set<String> zoneIds = ZoneId.getAvailableZoneIds();

        // print first record
        System.out.println("First ZoneId in list:" + zoneIds.iterator().next());
    }
}
```

**Output:**

```
First ZoneId in list:Asia/Aden

```

**程序 2:**

```
// Java program to demonstrate
// ZoneId.getAvailableZoneIds() method

import java.time.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // get available zones using zoneIds()
        Set<String> allZones = ZoneId.getAvailableZoneIds();

        // create ArrayList from Set
        List<String> zoneList = new ArrayList<String>(allZones);
        Collections.sort(zoneList);

        // printing first 5 zoneid with offset
        LocalDateTime dt = LocalDateTime.now();
        for (int i = 0; i < 5; i++) {

            // get zoneid then ZonedDateTime and offset
            // from that ZoneId
            String s = zoneList.get(i);
            ZoneId zoneid = ZoneId.of(s);
            ZonedDateTime zoneddate = dt.atZone(zoneid);
            ZoneOffset offset = zoneddate.getOffset();
            System.out.println("ZoneId = " + zoneid + " offset = " + offset);
        }
    }
}
```

**Output:**

```
ZoneId = Africa/Abidjan offset = Z
ZoneId = Africa/Accra offset = Z
ZoneId = Africa/Addis_Ababa offset = +03:00
ZoneId = Africa/Algiers offset = +01:00
ZoneId = Africa/Asmara offset = +03:00

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneid . html # getAvailableZoneIds(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#getAvailableZoneIds())