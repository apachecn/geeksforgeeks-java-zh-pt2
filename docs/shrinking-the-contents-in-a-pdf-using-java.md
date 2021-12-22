# 使用 Java 缩小 PDF 中的内容

> 原文:[https://www . geeksforgeeks . org/收缩 pdf 中的内容-使用-java/](https://www.geeksforgeeks.org/shrinking-the-contents-in-a-pdf-using-java/)

压缩 PDF 文档内容的程序。程序中需要导入外部 jar 文件。下面是相同的实现。

**进场:**

**1。创建一个空的 PDF 文件。**

*   将空 PDF 的路径分配给字符串变量。
*   从包装**com.itextpdf.kernel.pdf**进口 **PdfWriter** 。(PdfWriter 允许我们在 PDF 文件中写入内容)
*   PdfWriter 接受一个字符串变量作为其参数，该参数代表 PDF 的目标。
*   通过传递 PDF 文件的路径来初始化 PdfWriter 对象。

**2。创建一个表示空 PDF 文件的文档。**

*   从包装**com.itextpdf.kernel.pdf**导入**文件**。(PdfDocument 用于在代码中表示 pdf。这以后可用于添加或修改各种特征，例如字体、图像等)
*   PdfDocument 接受 PdfWriter 或 PdfReader 对象作为其参数。
*   通过传递 PdfWriter 对象初始化 PdfDocument。

**3。对原始 PDF 重复上述步骤。**

*   将原始 PDF 的路径分配给字符串变量。
*   从包装**com.itextpdf.kernel.pdf**进口 **PdfReader** 。(PdfReader 允许我们阅读 PDF 文件上的内容)
*   将原始 PDF 的路径传递给 PdfReader 构造函数。
*   通过传递 PdfReader 对象来初始化 PdfDocument。

**4。从原始 PDF 中获取页面的大小。**

*   从包装**com.itextpdf.kernel.pdf**中导入 **PdfPage** 。(PDF 页面代表 PDF 中的特定页面)
*   从包**中导入**矩形**。**
*   PdfDocumen **t** 类中的方法 **getPage(int pageNumber)** 返回指定特定页面的 PdfPage 对象。
*   PdfPage 类中的方法 **getPageSize()** 返回特定 PdfPage 对象的矩形对象。

**5。从空的 PDF 中获取页面的大小。**

*   无法从空的 PDF 中获取页面大小。
*   因此，为了获得大小，我们使用 PdfDocument 类中的 **addNewPage()** 方法向空 PDF 添加一个新页面。addNewPage()方法返回一个 PdfPage 对象。
*   PdfPage 类中的方法 **getPageSize()** 返回特定 PdfPage 对象的矩形对象。

**6。创建原始页面的缩小版本。**

*   从包**中导入**affinitetransform**。**
*   可以使用(emptyPageWidth/originalPageWidth)/2 计算新的缩放宽度。
*   可以使用(emptyPageHeight/originalPageHeight)/2 计算新的缩放高度。
*   affinitetransform 类中的**静态**方法**获取缩放实例(双倍宽度，双倍高度)**返回一个具有缩放宽度和缩放高度的 affinitetransform 对象。

**7。将原始页面的缩小版本附加到空的 PDF 中。**

*   从包**中导入 **PdfCanvas** 。**
*   通过传入空页面作为参数来初始化 PdfCanvas 对象。
*   将上面创建的具有缩放尺寸的矩阵添加到空白画布中。
*   使用 PdfPage 类中存在的方法**copy asFOrmxobject(PdFdDocument shrinkedDocument)**(返回一个**PdFpPage 类中的从原始页面复制内容。**
*   **使用方法**添加 XoObject(PdfXoObject XoObject，float x，float y)将复制的页面添加到画布上。****

****8。创建文档。****

*   **从包**中导入**文档** t。****
*   **创建一个文档对象，使 PDF 成为可读版本。**
*   **Document 类的一个构造函数接受 PdfDocument 对象作为它的参数。**
*   **通过将压缩文档作为参数传递来初始化文档对象。**
*   **创建对象后，文档被关闭，以防止内存泄漏。** 

****注意:** [外罐必选](https://jar-download.com/?search_box=com.itextpdf.layout)(点击此处下载)。**

**以下是 PDF 缩小的实现:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to shrink the contents of a PDF

// Importing the necessary libraries required
import com.itextpdf.kernel.pdf.*;
import com.itextpdf.kernel.geom.Rectangle;
import com.itextpdf.kernel.geom.AffineTransform;
import com.itextpdf.kernel.pdf.canvas.PdfCanvas;
import com.itextpdf.kernel.pdf.xobject.PdfFormXObject;
import com.itextpdf.layout.Document;
public class Main {

    public static void main(String[] args)
    {

        // Try catch block is used to handle File Exceptions
        try {
            // Destination of the empty PDF
            String shrunkenPath = "/home/mayur/newGFG.pdf";
            // Creating PDF writer object
            PdfWriter pdfWriter
                = new PdfWriter(shrunkenPath);
            // Creating a PdfDocument object for empty pdf
            PdfDocument shrunkenDocument
                = new PdfDocument(pdfWriter);

            // Destination of the original PDF
            String originalPath = "/home/mayur/GFG.pdf";
            // Creating PDF reader object
            PdfReader pdfReader
                = new PdfReader(originalPath);
            // Creating a PdfDocument object for original
            // pdf
            PdfDocument originalDocument
                = new PdfDocument(pdfReader);

            // Opening the first page of the original PDF
            PdfPage orignalPage
                = originalDocument.getPage(1);
            // Getting the height and width of the original
            // PDF
            Rectangle originalPDFSizes
                = orignalPage.getPageSize();

            // Adding a new page to the empty PDF
            PdfPage emptyPage
                = shrunkenDocument.addNewPage();
            // Getting the height and width of the empty PDF
            Rectangle emptyPDFsizes
                = emptyPage.getPageSize();

            // Scaling down the original Pdf page
            double width = emptyPDFsizes.getWidth()
                           / originalPDFSizes.getWidth();
            double height = emptyPDFsizes.getHeight()
                            / originalPDFSizes.getHeight();
            // Calculating the new width and height
            double newWidth = width / 2;
            double newHeight = height / 2;
            // Creating a matrix with new width and new
            // height
            AffineTransform affineTransform
                = AffineTransform.getScaleInstance(
                    newWidth, newHeight);

            // Creating an empty canvas
            PdfCanvas canvas = new PdfCanvas(emptyPage);
            // Adding the matrix created to the empty canvas
            canvas.concatMatrix(affineTransform);

            // Copying the content from the original PDF
            PdfFormXObject pageCopy
                = orignalPage.copyAsFormXObject(
                    shrunkenDocument);
            // Adding the copied page to the canvas
            canvas.addXObject(pageCopy, (float)newWidth,
                              (float)newHeight);

            // Creating a Document object to make the PDF
            // readable
            Document doc = new Document(shrunkenDocument);

            // Closing the documents to prevent memory leaks
            doc.close();
            originalDocument.close();
            System.out.println(
                "Shrunken PDF successfully created");
        }
        // Catching any unwanted Exceptions
        catch (Exception e) {
            System.err.println(e);
        }
    }
}
```

****执行前:****

**![](img/6e6d1e12c82fd41215f180f809af7251.png)

原始 PDF** 

****执行后:****

**![](img/64767c083d644614ccdb54037493b1d5.png)

内容缩小后的 PDF**