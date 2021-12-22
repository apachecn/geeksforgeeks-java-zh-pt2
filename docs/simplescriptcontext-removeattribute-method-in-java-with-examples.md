# Java 中的 SimpleScriptContext remove attribute()方法，带示例

> 原文:[https://www . geesforgeks . org/simplescriptcontext-remove attribute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simplescriptcontext-removeattribute-method-in-java-with-examples/)

SimpleScriptContext 类的 **removeAttribute()** 方法用于移除给定范围内的属性，属性和范围的名称作为参数传递。

**语法:**

```java
public Object removeAttribute(String name, int scope)

```

**参数:**该方法接受两个参数:

*   **名称**是属性的名称
*   **范围**是要移除属性的范围。

**返回值:**此方法返回移除的值。

**异常:**该方法抛出以下异常:

*   **NullPointRexception**:如果名称为空。
*   **IllegalArgumentException** :如果名称为空或者范围无效。

下面的程序说明了 simplescriptcontext . remove attribute()方法:
**程序 1:**

```java
// Java program to demonstrate
// SimpleScriptContext.removeAttribute() method

import javax.script.ScriptContext;
import javax.script.SimpleScriptContext;

public class GFG {
    public static void main(String[] args)
    {

        // create SimpleScriptContext object
        SimpleScriptContext simple
            = new SimpleScriptContext();

        // add some attribute
        simple.setAttribute(
            "name", "Value",
            ScriptContext.ENGINE_SCOPE);

        // remove using removeAttribute()
        Object removedObject
            = simple.removeAttribute(
                "name",
                ScriptContext.ENGINE_SCOPE);

        // print
        System.out.println("Removed Object :"
                           + removedObject);
    }
}
```

**Output:**

```java
Removed Object :Value

```

**程序 2:**

```java
// Java program to demonstrate
// SimpleScriptContext.removeAttribute() method

import javax.script.ScriptContext;
import javax.script.SimpleScriptContext;

public class GFG {
    public static void main(String[] args)
    {

        // create SimpleScriptContext object
        SimpleScriptContext simple
            = new SimpleScriptContext();

        // add some attribute
        simple.setAttribute("Team1", "India",
                            ScriptContext.ENGINE_SCOPE);
        simple.setAttribute("Team2", "Japan",
                            ScriptContext.ENGINE_SCOPE);
        simple.setAttribute("Team3", "Nepal",
                            ScriptContext.GLOBAL_SCOPE);

        // remove using removeAttribute()
        Object remove1
            = simple.removeAttribute(
                "Team1",
                ScriptContext.ENGINE_SCOPE);
        Object remove2
            = simple.removeAttribute(
                "Team2",
                ScriptContext.ENGINE_SCOPE);

        // print scopes of different teams
        System.out.println("Removed : " + remove1);
        System.out.println("Removed : " + remove2);
    }
}
```

**Output:**

```java
Removed : India
Removed : Japan

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/script/simplescriptcontext . html # remove attribute(Java . lang . string，int)](https://docs.oracle.com/javase/10/docs/api/javax/script/SimpleScriptContext.html#removeAttribute(java.lang.String, int))