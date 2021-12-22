# 甲骨文认证 Java 助理(OCA)考试准备

> 原文:[https://www . geesforgeks . org/Oracle-certified-Java-associate-OCA-考试准备/](https://www.geeksforgeeks.org/oracle-certified-java-associate-oca-exam-preparation/)

朋友们！我最近参加亚奥理事会考试，成绩 95%。在这里，我分享一些技巧和考试问题模式，这些一定会帮助你参加亚奥理事会考试。本次考试保证就以下题目提问，或者我们可以说陈述。
考试代码:1Z0-808

**1。必须练习 str1 == str2 和 str1.equals(str2) 之间的[差异。](https://www.geeksforgeeks.org/difference-equals-method-java/)**
**示例-1.1** :

```
class Test {
    public static void main(String[] args)
    {
        String s = new String("hello");
        String s2 = "hello";

        if (s == s2) {
            System.out.println("==");
        }

        if (s.equals(s2)) {
            System.out.println("equals");
        }
    }
}
```

**Output:**

```
equals

```

**原因**:因为 String 类等于方法比较对象，但是==运算符只比较引用。如果两个引用都指向同一个对象，那么只有==运算符返回 true。

**示例-1.2** :

```
class Test {
    public static void main(String[] args)
    {
        String s = new String("hello");
        String s2 = s;

        if (s == s2) {
            System.out.println("==");
        }

        if (s.equals(s2)) {
            System.out.println("equals");
        }
    }
}
```

**Output:**

```
==
equals

```

**原因**:因为两个引用都指向同一个对象，所以“==”被打印，如果两个引用都指向同一个对象，那么默认情况下它们是相等的，所以“等于”被打印。

**2。研究三进制运算符及其编译时错误。**

**示例-2.1** :

```
class Test {
    public static void main(String[] args)
    {
        int marks = 90;
        String result = marks > 35 ? "Pass" : "Fail";
        System.out.println(result);
    }
}
```

**Output:**

```
Pass

```

**示例-2.2** :

```
class Test {
    public static void main(String[] args)
    {
        int marks = 90;
        String result = marks > 60 ? "Pass with 1st div."
                        : marks < 50 ? "Pass with 2nd div." : 
                          marks < 40 ? "Pass with 3nd div.";
        System.out.println(result);
    }
}
```

**输出**:编译时错误
**原因**:标记< 40？"用 3nd div 传递。"没有完成。
**修正**:标记< 40？"用 3nd div 传递。"**:“失败”**。

**3。研究“字符串对象是不可变的”这一规则。**
**例-3.1** :

```
class Test {
    public static void main(String[] args)
    {
        String ta = "A ";
        ta = ta.concat("B ");
        String tb = "C ";
        ta = ta.concat(tb);
        ta.replace('C', 'D');
        ta = ta.concat(tb);
        System.out.println(ta);
    }
}
```

**Output:**

```
A B C C

```

**4。[λ表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)及其简化形式。**

Java Lambda 表达式语法:
(参数列表)- > {body}
**4.1 Lambda 表达式示例:无参数**

```
// This a java method
void printHello()
{
    System.out.println("Hello World ");
}

Or

// As lambda the above method can be written as below
() -> { System.out.println("Hello World "); };

Or

// {} is optional for single line statement
() -> System.out.println("Hello World ");
```

**4.2λ表达式示例:单参数**

```
// This a java method
void sayHello(String name)
{
    System.out.println("Hello " + name);
}

Or

(name) -> { System.out.println("Hello " + name); };

Or

// {} optional
(name) -> System.out.println("Hello " + name);

Or
// () optional for single input parameter.
name -> System.out.println("Hello " + name); 
```

**4.3λ表达式示例:多参数**

```
// This a java method
int add(int num1, int num2)
{
    return num1 + num2;
}

Or

(int num1, int num2) -> { return num1 + num2; };

Or

(int num1, int num2) -> num1 + num2;

Or 

// () mandatory for more than one input parameter.
(num1, num2) -> num1 + num2;
```

**5。研究&(按位与)和& &(逻辑与)运算符的区别。**
**例-5.1** :

```
class Test {
    public static void main(String[] args)
    {
        int a = 10;
        int b = 20;

        if (++a <= 10 && --b < 20) {}
          System.out.println("Output of && operator: "
                           + "a = " + a + " b = " + b);
        System.out.println("-------------");

        a = 10;
        b = 20;
        if (++a <= 10 & --b < 20) {}
          System.out.println("Output of & operator: "
                          + "a = " + a + " b = " + b);
    }
}
```

**Output:**

```
Output of && operator: a = 11 b = 20
-------------
Output of & operator: a = 11 b = 19

```

**原因**:因为 **' & & '** 运算符不会检查第二个操作数，如果第一个操作数的值为“假”。但是 **' & '** 必须检查两个操作数。

**注:**这些概念明确涵盖了亚奥理事会考试的 10-12 道题。