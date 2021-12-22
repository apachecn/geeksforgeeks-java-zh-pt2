# 使用 Java 将一个 PDF 拆分成多个

> 原文:[https://www . geesforgeks . org/split-a-pdf-in-multi-use-Java/](https://www.geeksforgeeks.org/splitting-a-pdf-into-many-using-java/)

将 PDF 文档拆分成多个 PDF 的程序。下面是使用 JAVA 的实现。这个题目的前提是你已经安装了 [**阿帕奇库**](https://pdfbox.apache.org/download.cgi)

**进场:**

*   从计算机加载 PDF。
    *   使用名为**的类加载 PDF 文档**。
    *   使用 PDdocument 类的 **load()** 函数加载文件。

*   运行拆分器类来拆分 PDF。
    *   **拆分器**是一个用来拆分 PDF 的类。
    *   使用拆分器类的 **Split()** 功能对 PDF 进行拆分。

*   使用迭代器对页面进行计数。
    *   将页面拆分成多个页面，以便在 **split()** 函数后计数页面，并使用该函数创建有限数量的拆分 PDF。
    *   保存所有 pdf。
    *   关闭文档。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Splitting a PDF in to many using Java
import org.apache.pdfbox.multipdf.Splitter;
import org.apache.pdfbox.pdmodel.PDDocument;

import java.io.File;
import java.io.IOException;
import java.util.List;
import java.util.Iterator;

public class SplitPdf {
    public static void main(String[] args)
        throws IOException
    {

        // Loading PDF
        File pdffile
            = new File("C:/Desktop/Java/sample.pdf");
        PDDocument document = PDDocument.load(pdffile);

        // Splitter Class
        Splitter splitting = new Splitter();

        // Splitting the pages into multiple PDFs
        List<PDDocument> Page = splitting.split(document);

        // Using a iterator to Traverse all pages
        Iterator<PDDocument> iteration
            = Page.listIterator();

        // Saving each page as an individual document
        int j = 1;
        while (iteration.hasNext()) {
            PDDocument pd = iteration.next();
            pd.save("C:/Desktop/Java/Generated/sample-"
                    + j++ + ".pdf");
        }
        System.out.println("Splitted Pdf Successfully.");
        document.close();
    }
}
```