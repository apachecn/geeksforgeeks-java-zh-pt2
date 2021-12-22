# Java 中的 number format getavailable locales()方法，示例

> 原文:[https://www . geesforgeks . org/number format-getavailable locales-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getavailablelocales-method-in-java-with-examples/)

**getAvailableLocales()** 方法是**[Java . text . NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/)**的内置方法，返回本地化 number format 实例可用的区域设置数组。因此，所有返回值都表示 Java 运行时支持的本地。

**语法** :

```java
public static Locale[] getAvailableLocales()
```

**参数**:函数不接受单个参数。

**返回值**:该函数返回本地化的 NumberFormat 实例可用的区域设置数组

下面是上述功能的实现:

**程序 1:**

```java
// Java program to implement
// the above function

import java.text.NumberFormat;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
        throws Exception
    {

        // Get all the available country names
        Locale[] arr
            = NumberFormat
                  .getAvailableLocales();

        // Iterate and print
        for (Locale it : arr) {
            System.out.println(
                it.getDisplayCountry()
                + " ");
        }
    }
}
```

**输出:**

```java
United Arab Emirates 
Jordan 
Syria 
Croatia 
Belgium 
Panama 
Venezuela 
Malta 

Taiwan 

Denmark 
Puerto Rico 
Vietnam 
United States 
Montenegro 
Sweden 
Singapore 
Bolivia 
Bahrain 

Saudi Arabia 

Yemen 
India 

Malta 
Finland 

Bosnia and Herzegovina 

Ukraine 
Switzerland 

Argentina 
Egypt 
Japan 
El Salvador 
Brazil 

Czech Republic 

Iceland 
Spain 
Poland 

Serbia and Montenegro 

Malaysia 

Spain 
Bulgaria 
Colombia 

Bosnia and Herzegovina 
Paraguay 

Ecuador 
United States 
Sudan 

Romania 
Philippines 

Tunisia 
Montenegro 
Guatemala 
Cyprus 
South Korea 

Mexico 
Russia 
Honduras 
Norway 
Hong Kong 
Hungary 
Thailand 
Iraq 
Chile 
Morocco 

Ireland 

Turkey 
Qatar 
Estonia 

Portugal 
Luxembourg 
Oman 

Albania 
Dominican Republic 
Cuba 

New Zealand 
Serbia 
Switzerland 
Uruguay 

Greece 
Israel 
South Africa 
Thailand 

France 
Austria 

Norway 
Australia 

Canada 
Latvia 
Netherlands 
Luxembourg 
Costa Rica 
Kuwait 
Libya 

Switzerland 

Germany 
Algeria 
Slovakia 
Italy 
Lithuania 
Ireland 
Singapore 
Canada 

Belgium 

China 
Japan 
Greece 
Serbia 

India 
Lebanon 
Nicaragua 

Belarus 
Macedonia 
Slovenia 
Peru 
Indonesia 
United Kingdom

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/text/numberformat . html # getavailable locales()](https://docs.oracle.com/javase/10/docs/api/java/text/NumberFormat.html#getAvailableLocales())