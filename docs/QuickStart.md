---
id: QuickStart
title: Quick Start
---
The following quick start sections help you in getting started with the GcPdf library:
   1. Create and save a PDF document
   2. Load and modify a PDF document
   
   ## Create and save a PDF document
   
This quick start helps you in getting started with the GcPdf library. It covers how to create a simple PDF document having    a single page and draw string on it in a specified font using a .NET Core or .NET Standard application. Follow the steps   below to get started:

  1. Create a new PDF document
  2. Draw a string on the PDF document
  3. Save the PDF document  
 
  ![hello world](assets/helloworld_GcPdf.png)
   
  ### Step 1: Create a new PDF document
  
  1. Create a new application (.NET Core Console App\Windows Forms App) and add the references.
  2. Include the following namespaces
  
     using GrapeCity.Documents.Pdf;  
     using GrapeCity.Documents.Text;
    
  Create a new PDF document using an instance of GcPdfDocument and define a text format for drawing a string, through code.
  
    C#  
    // Create a new PDF document:  
    GcPdfDocument doc = new GcPdfDocument();  
    // Add a page, and get its Graphics object to draw on:  
    GcPdfGraphics g = doc.NewPage().Graphics;  
    // Create a text format for the "Hello World!" string:  
    TextFormat tf = new TextFormat();  
    // Use standard Times font  
    tf.Font = StandardFonts.Times;  
    // Pick a font size:  
    tf.FontSize = 14;  
  
  ### Step 2: Draw a string on the PDF document
  Add the following code that uses DrawString method of GcGraphics class to draw string.

    C#
    // Draw the string at (1",1") from top/left of page
    //(72 dpi is the default PDF graphics' resolution):
    g.DrawString("Hello, World!", tf, new PointF(72, 72));
    

  ### Step 3: Save the document
  Save the document using Save method of the GcPdfDocument class.
  
  ```C#
    //Save PDF document
    doc.Save("filename.pdf");
 ``` 
  ## Load and modify a PDF document  This quick start covers how to load an existing PDF document, modify and save it using a .NET Core or .NET Standard application. Follow the steps below to get started:  

  1. Load an existing document in GcPdf  
  2. Modify the PDF document  
  3. Save the PDF document  
  
 ### Step 1: Load an existing document in GcPdf  
  1. Create a new application (.NET Core Console App\Windows Forms App) and add the references.  
  2. Include the following namespace  
         using GrapeCity.Documents.Pdf;  
  3. Load an existing document using Load method of the GcPdfDocument class.  
  
  ```C#   
  GcPdfDocument doc = new GcPdfDocument();  
  
  //Create an object of filestream   
  var fs = new FileStream(Path.Combine("DocAttachment.pdf"), FileMode.Open,FileAccess.Read);  
  //Load the document  
  doc.Load(fs);  
  ```
  ###  Step 2: Modify the document  
  1. Add a new page to the document using NewPage method of the GcPdfDocument class.  
  ``` C#   
  //Add a new page in the document  
  GcPdfGraphics g = doc.NewPage().Graphics;  
  ```
  2. Add the following code that uses DrawString method of GcGraphics class to draw string.  
  ``` C#  
  //Add text on the new page  
  g.DrawString("This is a newly added page in the modified document.", new TextFormat()  
  {  
       Font = StandardFonts.Times,  
       FontSize = 12  
  }, new PointF(72, 72));  
```    
  ### Step 3: Save the document  
  Save the document using Save method of the GcPdfDocument class.  
 
  ``` C#  
  //Save the document  
  doc.Save("ModifiedDocument.pdf");  
```  

