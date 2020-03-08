---
layout: post
title:  "pdfBox处理PDF文件"
date:   2020-03-07
tags:  zsc
categories: Java
---

* 将pdfBox引入项目

    ```gradle 
    implementation group: 'org.apache.pdfbox', name: 'pdfbox', version: '2.0.19'
    ```

* 将图像插入PDF文档
    * 您可以分别使用PDImageXObject和PDPageContentStream类的createFromFile()和drawImage()方法将图像插入PDF文档。

* 以下是从现有PDF文档中提取文本的步骤。

* 第1步:加载现有PDF文档
    * 使用PDDocument类的静态方法load()加载现有PDF文档。 此方法接受文件对象作为参数，因为这是一个静态方法，您可以使用类名调用它，如下所示。
    ```java
    File file = new File("path of the document")
    PDDocument doc = PDDocument.load(file);
    ```

* 第2步:检索页面
    * 选择PDF文档中的页面并使用getPage()方法检索其页面对象，如下所示。
    ```java
    PDPage page = doc.getPage(0);
    ```
* 第3步:创建PDImageXObject对象
    * PDFBox库中的类PDImageXObject表示图像。 它提供了执行与图像相关的操作所需的所有方法，例如插入图像，设置图像高度，设置图像宽度等。

    * 我们可以使用createFromFile()方法创建此类的对象。 对于这种方法，我们需要传递我们想要以字符串形式添加的图像的路径以及需要添加图像的文档对象。

    ```java
    PDImageXObject pdImage = PDImageXObject.createFromFile("C:/logo.png", doc);
    ```

* 第4步:准备内容流
    * 您可以使用名为PDPageContentStream的类的对象插入各种数据元素。 您需要将文档对象和页面对象传递给此类的构造函数，因此，通过传递在前面步骤中创建的这两个对象来实例化此类，如下所示。

    ```java
    PDPageContentStream contentStream = new PDPageContentStream(document, pdPage,PDPageContentStream.AppendMode.APPEND,true, true);
    ```

    * 以下为 PDPageContentStream 插入图片的构造方法的重载方法

    ```java
     /**
     * Create a new PDPage content stream.
     *
     * @param document The document the page is part of.
     * @param sourcePage The page to write the contents to.
     * @param appendContent Indicates whether content will be overwritten, appended or prepended.
     * @param compress Tell if the content stream should compress the page contents.
     * @param resetContext Tell if the graphic context should be reset. This is only relevant when
     * the appendContent parameter is set to {@link AppendMode#APPEND}. You should use this when
     * appending to an existing stream, because the existing stream may have changed graphic
     * properties (e.g. scaling, rotation).
     * @throws IOException If there is an error writing to the page contents.
     */
    public PDPageContentStream(PDDocument document, PDPage sourcePage, AppendMode appendContent,
                               boolean compress, boolean resetContext) throws IOException
    ```

* 第5步:在PDF文档中绘制图像
    * 您可以使用drawImage()方法在PDF文档中插入图像。 对于此方法，您需要添加在上面步骤中创建的图像对象和图像所需的尺寸（宽度和高度），如下所示。

    ```java
    // x y 为图片起点  width和height 为图片的宽和高
    contentStream.drawImage(pdImage,x, y, width, height);
    ```

* 第6步:关闭PDPageContentStream
    * 使用close()方法关闭PDPageContentStream对象，如下所示。

    ```java
    contentstream.close();
    ```

* 第7步:保存文档
    * 添加所需内容后，使用PDDocument类的save()方法保存PDF文档，如以下代码块所示。

    ```java
    doc.save("Path");
    //重载方法
    doc.save(new File())
    ```

* 第8步:关闭文档
    * 最后，使用PDDocument类的close()方法关闭文档，如下所示。
    ```java
    doc.close();
    ```
