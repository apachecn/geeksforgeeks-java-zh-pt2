# 使用 BFS 遍历 Java 中的目录

> 原文:[https://www . geesforgeks . org/遍历-目录-Java-使用-bfs/](https://www.geeksforgeeks.org/traversing-directory-java-using-bfs/)

给定一个目录，打印以给定目录为根的目录树中的所有文件和文件夹。

我们可以使用以下步骤在 [BFS](https://www.geeksforgeeks.org/breadth-first-traversal-for-a-graph/) 中迭代遍历目录。我们创建一个空队列，并首先对给定的目录路径进行排队。当队列不为空时，我们运行循环。我们从队列中取出一个项目。如果弹出的项目是一个目录，获取其中所有文件和目录的列表，将每个目录添加到队列中。如果弹出的项目是一个文件，我们打印它的名称。

```java
// Java program to print all files/directories
// present in a directory.
import java.io.File;
import java.util.LinkedList;
import java.util.Queue;

class FileUtils {

    public static void printDirsFiles(String inputDir)
    {
        /* make a queue to store files and directories */
        Queue<File> queue = new LinkedList<>();

        queue.add(new File(inputDir));

        /* loop until queue is empty -*/
        while (!queue.isEmpty()) {

            /* get next file/directory from the queue */
            File current = queue.poll();

            File[] fileDirList = current.listFiles();

            if (fileDirList != null) {

                /* Enqueue all directories and print 
                   all files. */
                for (File fd : fileDirList) {
                    if (fd.isDirectory()) 
                        queue.add(fd);
                    else 
                        System.out.println(fd);                    
                }
            }
        }
    }

    /* Iterative function to traverse given 
       directory in Java using BFS*/
    public static void main(String[] args)
    {
        String inputDir = "C:\\Programs";
        printDirsFiles(inputDir);
    }
}
```

本文由**普拉纳夫**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。