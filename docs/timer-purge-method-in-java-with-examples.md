# Java 中的定时器清除()方法，示例

> 原文:[https://www . geesforgeks . org/timer-purge-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timer-purge-method-in-java-with-examples/)

Java 中 **[定时器类](https://www.geeksforgeeks.org/java-util-timer-class-java/)** 的 **purge()** 方法用于从定时器的这个队列中移除所有被取消的任务。时间的行为不受此方法调用的影响。

**语法:**

```java
public int purge()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回已经从队列中删除的**任务数**。

下面的程序说明了 Java 中 purge()方法的工作原理:

**程序 1:**

```java
// Java code to illustrate purge()

import java.util.*;

public class Java_Timer_Demo {
    public static void main(String args[])
    {

        // Creating the timer task, timer
        Timer time = new Timer();

        TimerTask timetask = new TimerTask() {

            public void run()
            {

                for (int i = 1; i <= 15; i++) {

                    System.out.println("Working on the task");

                    if (i >= 7) {
                        System.out.println("Stopping the task");
                        time.cancel();
                        break;
                    }
                }

                // purging the timer
                System.out.println("The Purge value:"
                                   + time.purge());
            };
        };

        time.schedule(timetask, 1500, 2000);
    }
}
```

**输出:**

```java
Working on the task
Working on the task
Working on the task
Working on the task
Working on the task
Working on the task
Working on the task
Stopping the task
The Purge value:0

```

**程序二:**

```java
// Java code to illustrate purge()

import java.util.*;

public class Java_Timer_Demo {

    public static void main(String args[])
    {

        // Creating the timer task, timer
        Timer time = new Timer();

        TimerTask timetask = new TimerTask() {
            public void run()
            {

                for (int i = 1; i <= 5; i++) {

                    System.out.println("Working on the task");

                    if (i >= 2) {

                        System.out.println("Stopping the task");
                        time.cancel();
                    }
                }

                // Purging the timer
                System.out.println("The Purge value:"
                                   + time.purge());
            };
        };

        time.schedule(timetask, 1, 1000);
    }
}
```

**输出:**

```java
Working on the task
Working on the task
Stopping the task
Working on the task
Stopping the task
Working on the task
Stopping the task
Working on the task
Stopping the task
The Purge value:0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/timer . html # purge–](https://docs.oracle.com/javase/9/docs/api/java/util/Timer.html#purge--)