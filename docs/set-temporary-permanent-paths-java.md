# 如何在 Java 中设置临时路径和永久路径

> 原文:[https://www . geesforgeks . org/set-暂存-永久-路径-java/](https://www.geeksforgeeks.org/set-temporary-permanent-paths-java/)

如果 [Java](https://www.geeksforgeeks.org/java/) 源文件在 jdk/bin 文件夹内，则不需要设置路径，因为像 javac、Java 这样的工具在当前文件夹内。
但是如果 java 源文件在 jdk/bin 文件夹之外，则需要设置路径才能执行 java 源文件。
设置 java 路径有两种方式:

1.  暂时的
2.  永久的

1.  **Setting Temporary Java Path:**

    要设置临时 java 路径:

    *   打开命令提示符
    *   复制 jdk/bin 目录的路径
    *   在命令提示符下写入:SET PATH = copy _ PATH

    **例如:**

    ```java
    SET PATH=C:\Program Files\Java\jdk1.7.0_79\bin
    ```

    ![](img/af3e595e847cac928daa02f2969505c7.png)

2.  **Setting Permanent Java Path:**

    要设置永久 java 路径:

    1.  **Go to MyPC properties**

        ![](img/69bf48f513cdda507ce7a5a6f852deaf.png)

    2.  **Click on Advanced system settings**

        ![](img/a66be9f57bd7273be4c44b727dc207fe.png)

    3.  **Click on Environment Variables**

        ![](img/bde11d314bf8f8a8d8823b89a7b59f12.png)

    4.  **Click on New tab of User variables**

        ![](img/c6450cc61d07e37fd0b628422a930bed.png)

    5.  **Assign value Gfg_path to Variable name:**

        ![](img/7b0e811b64f3e372c998f48dfdf1e216.png)

    6.  **Copy the path of bin folder**

        ![](img/b5814a21470ad554f272f95fad16a52b.png)

    7.  **Paste path of bin folder in Variable value:**

        ![](img/1490af53f7c38376271a73f870ea3b71.png)

    8.  **Click on OK button**

        ![](img/e3df730a51fb3f38f17bd3f6fb207493.png)

    9.  **Click on OK button**

        ![](img/567f09755ca5e8058a0c0d79a0e17d18.png)

        ```java
        In this way Temporary and Permanent Path for Java can be set in Windows.
        ```