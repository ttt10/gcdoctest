---
id: GettingStarted
title: Getting Started
---

This topic incorporates:

-   [System
    requirements](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GettingStarted.html#i-in-this-topic-f32cf590-8728-4311-91ab-d38bcac11971)

-   [Setting up an
    application](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GettingStarted.html#i-in-this-topic-a5755b3a-62c1-4974-b2a0-8053101bcd82)

-   [Quick
    Start](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GettingStarted.html#i-in-this-topic-51ad7f94-9158-4eb9-a195-c4d9d5d51b26)

System requirements
-------------------

-   .NET Standard 2.0

-   Visual Studio 2017/Visual Studio for MAC/Visual Studio Code for Linux

For OS versions supported in .NET Core 2.0, see [.NET Core 2.0 - Supported OS
versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).

Setting up an application
-------------------------

GcPdf references are available through NuGet, a Visual Studio extension that
adds the required libraries and references to your project automatically. To
work with GcPdf, you need to have following references in your application:

| Reference                                                                          | Purpose                                                                                                                                                                                                                                                                    |
|------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [GrapeCity.Documents.Pdf](https://www.nuget.org/packages/GrapeCity.Documents.Pdf/) | To use GcPdf in an application, you need to reference (install) just the GrapeCity.Documents.Pdf package. It will pull in the required infrastructure packages.                                                                                                            |
| GrapeCity.Documents.BarCode                                                        | To render barcodes, install the GrapeCity.Documents.Barcode (aka GcBarcode) package. It provides extension methods allowing to render barcodes when using GcPdf.                                                                                                           |
| GrapeCity.Documents.Common                                                         | GrapeCity.Documents.Common is an infrastructure package used by GcPdf and GcBarcode. You do not need to reference it directly.                                                                                                                                             |
| GrapeCity.Documents.Common.Windows                                                 | On a Windows system, you can optionally install GrapeCity.Documents.Common.Windows. It provides support for font linking specified in the Windows registry, and access to native Windows imaging APIs, improving performance and adding some features (e.g. TIFF support). |
| GrapeCity.Documents.DX.Windows                                                     | GrapeCity.Documents.DX.Windows is an infrastructure package used by GrapeCity.Documents.Common.Windows. You do not need to reference it directly.                                                                                                                          |

>   Note: There is a limitation of Xamarin iOS libraries that it does not
>   provide System.Drawing.Color by default. Therefore, to use
>   System.Drawing.Color with GcPdf on Xamarin.iOS, you need to add reference to
>   OpenTK-1.0.

### Add reference to GcPdf in your application from NuGet.org

In order to use GcPdf in a .NET Core, ASP.NET Core, .NET Framework application
(any target that supports .NET Standard 2.0), install the NuGet packages in your
application using the following steps:

Visual Studio for Windows:

1.  Open Visual Studio for Windows.

2.  Create any application (any target that supports .NET Standard 2.0).

3.  Right-click the project in Solution Explorer and choose Manage NuGet
    Packages.

4.  In the Package source on top right, select nuget.org.

5.  Click Browse tab on top left and search for "Grapecity.Documents".

6.  On the left panel, select GrapeCity.Documents.Pdf

7.  On the right panel, click Install.

    ![](../website/static/img/Nuget_Image.png)

8.  Choose **Accept** in the next screen.

9.  (Optional)If you want to add barcodes in your PDF file, you need to install
    the package **GrapeCity.Documents.Barcode** using the steps 5 to 8 above.

This will add all the required references of the package to your application.
After this step, follow the steps in the [Quick
Start](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GettingStarted.html#QS) section
below.


Visual Studio for Mac


1.  Open Visual Studio for MAC.

2.  Create any application (any target that supports .NET Standard 2.0).

3.  In tree view on the left, right-click **Dependencies** and choose **Add
    Packages**.

4.  In the Search panel, type "GrapeCity.Documents".

5.  From the list of packages displayed in the left panel, select
    **GrapeCity.Documents.Pdf** (and **GrapeCity.Documents.Barcode** if you want
    to render barcodes in your Pdfs) and click **Add Packages**.

6.  Click **Accept**.

 

This will automatically add references of the package and its dependencies to
your application. After this step, follow the steps in the [Quick
Start](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GettingStarted.html#QS)
section below.

 


Visual Studio Code for Linux


1.  Open Visual Studio Code.

2.  Install **Nuget Package Manager** from **Extensions**.

3.  Create a folder "MyApp" in your **Home** folder.

4.  In the Terminal in Visual Studio Code, type "`cd MyApp`"

5.  Type command "`dotnet new console`"  
    *Observe*: This creates a .NETCore application with MyApp.csproj file and
    Program.cs.

6.  Press **Ctrl+P**. A command line opens at the top.

7.  Type command: "`>`"  
    *Observe*: "**Nuget Package Manager: Add Package**" option appears.

8.  Click the above option.

9.  Type "**Grapecity**" and press Enter.  
    *Observe*: GrapeCity packages get displayed in the dropdown.

10. Choose **GrapeCity.Documents.Pdf**.

11. (Optional) Repeat above steps to add **GrapeCity.Documents.Barcode** if you
    want to add barcodes to your PDF.  
    *Observe*: The packages would be added to your .csproj file.

12. Type following command in the Terminal window: "`dotnet restore`"

This will add references of the package to your application. After this step,
follow the steps in the [Quick
Start](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GettingStarted.html#QS) section
below.

### Quick Start

This quick start helps you in getting started with the GcPdf library. It covers
how to create a simple PDF document having a single page and draw string on it
in a specified font using a .NET Core or .NET Standard application. Follow the
steps below to get started:

 

1.  [Create a new PDF
    document](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GettingStarted.html#step1)

2.  [Draw a string on the PDF
    document](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GettingStarted.html#step2)



![](../website/static/img/helloworld_GcPdf.png)

### Step 1: Create a new PDF document

1.  Create a new application (.NET Core Console App\\Windows Forms App) and add
    the references.

2.  Include the following namespaces

    -   using GrapeCity.Documents.Pdf;

    -   using GrapeCity.Documents.Text;

3.  Create a new PDF document using an instance
    of [GcPdfDocument](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.GcPdfDocument.html)
    and define a text format for drawing a string, through code.

>   C#

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
// Create a new PDF document: GcPdfDocument doc = new GcPdfDocument(); 
// Add a page, and get its Graphics object to draw on: 
GcPdfGraphics g = doc.NewPage().Graphics; 
// Create a text format for the "Hello World!" string: 
TextFormat tf = new TextFormat(); 
// Use standard Times font 
tf.Font = StandardFonts.Times; 
// Pick a font size: 
tf.FontSize = 14;
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

### Step 2: Draw a string on the PDF document

1.  Add the following code that
    uses [DrawString](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Common~GrapeCity.Documents.Drawing.GcGraphics~DrawString.html)
    method
    of [GcGraphics](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Common~GrapeCity.Documents.Drawing.GcGraphics.html)
    class to draw string.

    
    >C#
    

    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    // Draw the string at (1",1") from top/left of page 
    //(72 dpi is the default PDF graphics' resolution): 
    g.DrawString("Hello, World!", tf, new PointF(72, 72));
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

2.  Save the PDF document using the following code.

   
    >C#
    
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    //Save PDF document 
    doc.Save("filename.pdf");
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
