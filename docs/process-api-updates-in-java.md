# 用 Java 处理 API 更新

> 原文:[https://www.geeksforgeeks.org/process-api-updates-in-java/](https://www.geeksforgeeks.org/process-api-updates-in-java/)

通过流程应用编程接口，我们可以执行与流程相关的任何操作。
假设如果我们想要当前正在运行的进程的进程 id，或者我们想要创建一个新的进程，或者想要销毁已经在运行的进程，或者想要找到当前正在运行的进程的子进程和父进程，或者如果我们想要获得关于一个进程的任何信息，那么我们可以使用 Process API 更新。
**Java 9 流程 API 更新:–**

*   java.lang 包中的 Process 类增加了一些新方法。
    Process 类是 Process API 中的一个老类，java 9 中只增加了一些方法，比如，pid()，info()等。
*   像 startPipeline()这样的方法被添加到 ProcessBuilder 类中，该类已经存在于旧的 java 版本中。
*   ProcessHandle(I):这是 java 9 中新增的一个接口。它用于处理一个过程。
*   ProcessHandle。Info(I):它是一个内部接口，它提供与一个流程相关的所有信息。

**流程处理(I):**

*   要获取当前正在运行的进程的 ProcessHandle 对象:

```
ProcessHandle ph = ProcessHandle.current();
```

*   要获取给定进程对象的进程句柄:

```
ProcessHandle ph = p.toHandle(); //p is a process object
```

*   要从给定的进程标识获取进程句柄对象:

```
Optional obj = ProcessHandle.of(PID);
ProcessHandle ph = obj.get();
```

*   //获取进程句柄对象
    这里 process handle 对象的返回类型是可选的，因为进程可能存在，也可能不存在。
    如果进程存在，那么我们将获得它的 ProcessHandle 对象，否则我们不会获得它的 ProcessHandle 对象。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class Demo {

    public static void main(String[] args)
    {
        ProcessHandle ph = ProcessHandle.current();
        long id = obj.pid();
        System.out.println("Id of the current process is : " + id);
    }
}
```

```
Id of the current process is : 5420
```

**ProcessHandle。信息(一):–**
信息是存在于 ProcessHandle 接口内部的一个内部接口。
我们可以获得给定或当前运行进程的完整信息。
创建进程句柄。信息对象:–
为此，首先我们需要创建 ProcessHandle 对象，然后我们将创建 ProcessHandle。信息对象。

```
ProcessHandle ph = ProcessHandle.current();
ProcessHandle.Indo pinfo = ph.info();
```

ProcessHandle 中的方法。信息(一):-

*   user():–
    返回当前流程的用户。

```
Optional o = info.user();
System.out.println("User is : "+o.get());
```

*   command():–
    返回启动进程的命令。

```
Optional o = info.command();
System.out.println("Command is : "+o.get());
```

*   startInstant():–
    返回当前进程开始的时间。

```
Optional o = info.startInstant();
System.out.println("Time of process start is : "+o.get());
```

*   totalcpudduration():–
    返回当前进程的总 CPU 持续时间。

```
Optional o = info.totalCpuDuration();
System.out.println("Total CPU duration is : "+o.get());
```

**示例:–**

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class Demo {

    public static void main(String[] args)
    {
        ProcessHandle ph = ProcessHandle.current();
        ProcessHandle.Info pinfo = ph.info();
        System.out.println("Complete process information is :" + pinfo);
        System.out.println("User of the process is : " + pinfo.user().get());
        System.out.println("Command used is : " + pinfo.command().get());
        System.out.println("Time of process starting is : " + pinfo.startInstant().get());
        System.out.println("Total CPU Duration is : " + pinfo.totalCpuDuration().get());
    }
}
```