---
id: Annotations
topic: Annotations
---
An annotation is a visual element to mark or highlight specific location on a page. It can be text, image, shape, or an attachment that can be used to display, highlight and refer to a particular information. The purpose of using annotation is to simply associate information or a note with an item or location on a page. A number of annotations can be displayed either in open or closed state. In the closed state, they appear on the page as a note, icon, or a box, depending on the annotation type. When opened by clicking, these annotations display the associated object such as pop up window having text. For more information on annotations and its types, see PDF specification 1.7 (Section 12.5).

GcPdf offers a variety of standard annotation types as described below.

#### Text annotation  
GcPdf provides TextAnnotation class that lets you display the annotation as a sticky note attached to a location in a PDF document. This annotation appears as an icon in closed state, which on clicking displays a pop-up window with associated text in the open state.

#### Free text annotation  
GcPdf offers FreeTextAnnotation class that allows you to display the text directly on the page instead of displaying the associated note in the pop-up window.

#### Stamp annotation  
GcPdf provides StampAnnotation class which lets you display text or graphics, intended to look as if stamped on the page.

#### Circle annotation  
GcPdf provides CircleAnnotation class to display a circle or an ellipsis on the page which when clicked opens a pop-up window containing the text of the associated note.

#### Square annotation  
GcPdf offers SquareAnnotation class to display a rectangle on the page which when clicked opens a pop-up window containing the associated text.

#### Polygon annotation  
GcPdf provides PolygonAnnotation class to display a polygon on the page which when clicked opens a pop-up window containing the associated text.

#### Line annotation  
GcPdf provides LineAnnotation class to display a straight line on the page which when clicked opens a pop-up window containing the text of the associated note.

#### File attachment annotation  
GcPdf offers FileAttachmentAnnotation class to reference a file embedded in the document.

#### Watermark annotation  
GcPdf allows displaying graphics on a page at a fixed position with fixed size regardless of the dimensions of the page using WatermarkAnnotation class.

#### Widget annotation  
GcPdf provides WidgetAnnotation class that represents a field for managing user interaction, usually used in interactive forms.


All the listed annotations have a dedicated class and properties in the GcPdf library which makes it easier to implement different annotations. GcPdf also allows you to specify various characteristics of annotation such as visibility, printing, etc. using Flags property that accepts the values from AnnotationFlags enum.

    C#
    var textAnnot = new TextAnnotation()
    {
        Contents = "This is an annotation in red color.",
        Name = "Text Annotation",
        Rect = new RectangleF(72, 72, 72 * 2, 72),
        Color = Color.Red,
    };
    //Add the text annotation
    page.Annotations.Add(textAnnot);
    

#### Get Annotations  
To get the annotations from a page:

    1.  Create an instance of the AnnotationCollection class.  
    2.  Use the AnnotationCollection object to access the annotation by specifying its index.
    
    C#
    //Get Annotation
    AnnotationCollection acol = doc.Pages[0].Annotations;
    // Display the property values
    Console.WriteLine("Annotation Type: {0}", acol[0].Name);
    
    
#### Modify Annotations
To modify the annotation, you can set the properties of the type of annotation you used on a page. For instance, setting Contents and Color property of the TextAnnotation class modifies the existing content and color of the annotation.

    C#
    //Modify annotation
    textAnnot.Color = Color.BlueViolet;
    textAnnot.Contents = "This is a Text annotation.";
    

#### Delete Annotations
To delete all the annotations from a page, use the Clear method. Apart from this, RemoveAt method can be used to remove a particular annotation by specifying its index value.

    C#
    // Delete all annotations
    page.Annotations.Clear();  
    // Delete a particular annotation
    page.Annotations.RemoveAt(0);
