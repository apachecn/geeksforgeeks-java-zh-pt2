# 使用 Java 设置图像在 PDF 文档中的位置

> 原文:[https://www . geesforgeks . org/setting-the-position-of-image-in-pdf-document-use-Java/](https://www.geeksforgeeks.org/setting-the-position-of-the-image-in-pdf-document-using-java/)

要使用 Java 设置图像在 PDF 文档中的位置，需要先下载多个外部依赖项。使用 iText 库设置图像在 PDF 中的位置。这些是使用 java 设置图像在 PDF 中的位置应该遵循的步骤。

**1。创建 PdfWriter 对象:**PDF writer 类表示 PDF 的文档编写器。这个类的构造函数接受一个字符串，即创建 PDF 的文件的路径。

**2。创建 PdfDocument 对象:**PdfDocument 类是 iText 中表示 PDF Document 的类，要以写模式实例化这个类，需要将类 pdfwriter(即上面代码中的 PdfWriter)的一个对象传递给它的构造函数。

**3。创建文档对象:**文档类是创建自给自足的 PDF 时的根元素。这个类的一个构造函数接受一个类 PdfDocument(即 pdfdocument)的对象。

**4。创建图像对象:**我们需要图像对象来管理图像。为了创建一个图像对象，我们需要创建一个图像数据对象。我们可以绕过字符串参数来创建它，该参数表示 ImageDataFactory 类的 create()方法要创建的图像的路径。现在，我们可以通过将 imageData 对象作为参数传递给 Image 类的构造函数来创建一个 Image 对象。
T3【5。设置图像的位置:我们将使用图像的 setFixedPosition()方法来设置图像在 PDF 文档中的位置。我们将所需的位置坐标传递给 setFixedPosition()方法。

**6。向 Pdf 文档添加图像:**使用 Document 类的 Add()方法添加图像对象，使用 Document 类的 close()方法关闭文档。
**以下是执行程序所需的依赖项:**

```
io-7.1.13.jar
kernel-7.1.13.jar
layout-7.1.13.jar
```

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Setting the Position of the Image
// in PDF Document using Java
import com.itextpdf.io.image.ImageData;
import com.itextpdf.io.image.ImageDataFactory;

import com.itextpdf.kernel.pdf.PdfDocument;
import com.itextpdf.kernel.pdf.PdfWriter;

import com.itextpdf.layout.Document;
import com.itextpdf.layout.element.Image;

public class SetImagePosition {
    public static void main(String args[]) throws Exception
    {
        try {
            // path where the pdf is to be created.
            String path = "F:/JavaPdf/setImagePosition.pdf";
            PdfWriter pdfwriter = new PdfWriter(path);

            // Creating a PdfDocument object.
            // passing PdfWriter object constructor
            PdfDocument pdfdocument
                = new PdfDocument(pdfwriter);

            // Creating a Document and
            // passing pdfDocument object
            Document document = new Document(pdfdocument);

            // Create an ImageData object
            String imageFile = "F:/JavaPdf/image.png";
            ImageData data
                = ImageDataFactory.create(imageFile);
            // Creating an Image object
            Image image = new Image(data);

            // Set the position of the image.
            image.setFixedPosition(200, 300);

            // Adding image to the document
            document.add(image);
            // Closing the document
            document.close();

            System.out.println(
                "Image  position set successfully in pdf");
        }
        catch (Exception e) {
            System.out.println(
                "unable to set image position due to " + e);
        }
    }
}
```

**输出:**

```
Image  position set successfully in pdf
```

**PDF:**

![](img/28303ce6dd8fa58d11f083eb8d48141b.png)