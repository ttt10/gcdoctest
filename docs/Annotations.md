<div id="i-body-content" class="i-body-content" style="margin-left: 8px; margin-right: 8px; margin-top: 0.5em; font-family: &quot;Open Sans&quot;, &quot;Segoe UI&quot;, Verdana, Arial, Helvetica, sans-serif; font-size: 14px;"><p>An annotation is a visual element to mark or highlight specific location on a page. It can be text, image, shape, or an attachment that can be used to display, highlight and refer to a particular information. The purpose of using annotation is to simply associate information or a note with an item or location on a page. A number of annotations can be displayed either in open or closed state. In the closed state, they appear on the page as a note, icon, or a box, depending on the annotation type. When opened by clicking, these annotations display the associated object such as pop up window having text. For more information on annotations and its types, see [PDF specification 1.7](https://www.adobe.com/content/dam/acom/en/devnet/pdf/pdfs/PDF32000_2008.pdf ) (Section 12.5).</p><p style="margin-top: -6px;">GcPdf offers a variety of standard annotation types as described below.</p><dl><dt><strong>Text annotation</strong></dt><dd style="margin-left: 2em;">GcPdf provides [TextAnnotation](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.TextAnnotation.html ) class that lets you display the annotation as a sticky note attached to a location in a PDF document. This annotation appears as an icon in closed state, which on clicking displays a pop-up window with associated text in the open state.

</dd><dt><strong>Free text annotation</strong></dt><dd style="margin-left: 2em;">GcPdf offers [FreeTextAnnotation](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.FreeTextAnnotation.html ) class that allows you to display the text directly on the page instead of displaying the associated note in the pop-up window.

</dd><dt><strong>Stamp annotation</strong></dt><dd style="margin-left: 2em;">GcPdf provides [StampAnnotation](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.StampAnnotation.html ) class which lets you display text or graphics, intended to look as if stamped on the page.

</dd><dt><strong>Circle annotation</strong></dt><dd style="margin-left: 2em;">GcPdf provides [CircleAnnotation](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.CircleAnnotation.html ) class to display a circle or an ellipsis on the page which when clicked opens a pop-up window containing the text of the associated note.

</dd><dt><strong>Square annotation</strong></dt><dd style="margin-left: 2em;">GcPdf offers [SquareAnnotation](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.SquareAnnotation.html ) class to display a rectangle on the page which when clicked opens a pop-up window containing the associated text.

</dd><dt><strong>Polygon annotation</strong></dt><dd style="margin-left: 2em;">GcPdf provides [PolygonAnnotation](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.PolygonAnnotation.html ) class to display a polygon on the page which when clicked opens a pop-up window containing the associated text.

</dd><dt><strong>Line annotation</strong></dt><dd style="margin-left: 2em;">GcPdf provides [LineAnnotation](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.LineAnnotation.html ) class to display a straight line on the page which when clicked opens a pop-up window containing the text of the associated note.

</dd><dt><strong>File attachment annotation</strong></dt><dd style="margin-left: 2em;">GcPdf offers [FileAttachmentAnnotation](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.FileAttachmentAnnotation.html ) class to reference a file embedded in the document.

</dd><dt><strong>Watermark annotation</strong></dt><dd style="margin-left: 2em;">GcPdf allows displaying graphics on a page at a fixed position with fixed size regardless of the dimensions of the page using [WatermarkAnnotation](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.WatermarkAnnotation.html ) class.

</dd><dt><strong>Widget annotation</strong></dt><dd style="margin-left: 2em;">GcPdf provides [WidgetAnnotation](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.WidgetAnnotation.html ) class that represents a field for managing user interaction, usually used in interactive forms.
</dd></dl><p>All the listed annotations have a dedicated class and properties in the GcPdf library which makes it easier to implement different annotations. GcPdf also allows you to specify various characteristics of annotation such as visibility, printing, etc. using <strong>Flags</strong> property that accepts the values from [AnnotationFlags](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.AnnotationFlags.html ) enum.</p><p style="margin-top: -6px;">![annotation.png](content/images/annotation.png)
</p><h1 style="font-size: 1.538em; color: rgb(63, 82, 156);">Add Annotations[]( )
<p>GcPdf allows you to add annotations to a page in the PDF document. These annotations reside in the [Page](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Page.html ) object on which they are placed.</p><p style="margin-top: -6px;">To add an annotation on a page:</p>

1. Create an instance of class corresponding to annotation type you want to add to a page, for example, TextAnnotation class.


1. Call the Add method to add the annotation on the page.
<div class="i-filtered-content-CS" data-title="CS" data-itemid="CS">C#|<div class="i-copy-code-wrapper" style="position: relative;"><span class="i-copy-code btn btn-mini btn-xs" style="cursor: pointer; padding-left: 18px; background-image: url(&quot;../images/i-copy-code.png&quot;); background-repeat: no-repeat; background-position-y: 1px;">Copy Code</span>
|
-|-|
`<span style="color: rgb(0, 0, 255);">var</span> textAnnot = <span style="color: rgb(0, 0, 255);">new</span> TextAnnotation()
{
    Contents = <span style="color: rgb(128, 0, 0);">"This is an annotation in red color."</span>,
    Name = <span style="color: rgb(128, 0, 0);">"Text Annotation"</span>,
    Rect = <span style="color: rgb(0, 0, 255);">new</span> RectangleF(72, 72, 72 * 2, 72),
    Color = Color.Red,
};
<span style="color: rgb(0, 128, 0);">//Add the text annotation
</span>page.Annotations.Add(textAnnot);
`|

[Back to Top](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/Annotations.html#top )<h1 style="font-size: 1.538em; color: rgb(63, 82, 156);">Get Annotations[]( )
<p>To get the annotations from a page:</p>

1. Create an instance of the [AnnotationCollection](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.AnnotationCollection.html ) class.


1. Use the AnnotationCollection object to access the annotation by specifying its index.
<div class="i-filtered-content-CS" data-title="CS" data-itemid="CS">C#|<div class="i-copy-code-wrapper" style="position: relative;"><span class="i-copy-code btn btn-mini btn-xs" style="cursor: pointer; padding-left: 18px; background-image: url(&quot;../images/i-copy-code.png&quot;); background-repeat: no-repeat; background-position-y: 1px;">Copy Code</span>
|
-|-|
`<span style="color: rgb(0, 128, 0);">//Get Annotation
</span>AnnotationCollection acol = doc.Pages[0].Annotations;
<span style="color: rgb(0, 128, 0);">// Display the property values
</span>Console.WriteLine(<span style="color: rgb(128, 0, 0);">"Annotation Type: {0}"</span>, acol[0].Name);
`|

[Back to Top](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/Annotations.html#top )<h1 style="font-size: 1.538em; color: rgb(63, 82, 156);">Modify Annotations[]( )
<p>To modify the annotation, you can set the properties of the type of annotation you used on a page. For instance, setting [Contents](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.MarkupAnnotation~Contents.html ) and [Color](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/GrapeCity.Documents.Pdf~GrapeCity.Documents.Pdf.Annotations.MarkupAnnotation~Color.html ) property of the TextAnnotation class modifies the existing content and color of the annotation.</p><div class="i-filtered-content-CS" data-title="CS" data-itemid="CS">C#|<div class="i-copy-code-wrapper" style="position: relative;"><span class="i-copy-code btn btn-mini btn-xs" style="cursor: pointer; padding-left: 18px; background-image: url(&quot;../images/i-copy-code.png&quot;); background-repeat: no-repeat; background-position-y: 1px;">Copy Code</span>
|
-|-|
`<span style="color: rgb(0, 128, 0);">//Modify annotation
</span>textAnnot.Color = Color.BlueViolet;
textAnnot.Contents = <span style="color: rgb(128, 0, 0);">"This is a Text annotation."</span>;
`|

[Back to Top](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/Annotations.html#top )<h1 style="font-size: 1.538em; color: rgb(63, 82, 156);">Delete Annotations[]( )
<p>To delete all the annotations from a page, use the [Clear](https://msdn.microsoft.com/en-us/library/ms132405(v=vs.110).aspx ) method. Apart from this, [RemoveAt](https://msdn.microsoft.com/en-us/library/ms132414(v=vs.110).aspx ) method can be used to remove a particular annotation by specifying its index value.</p><div class="i-filtered-content-CS" data-title="CS" data-itemid="CS">C#|<div class="i-copy-code-wrapper" style="position: relative;"><span class="i-copy-code btn btn-mini btn-xs" style="cursor: pointer; padding-left: 18px; background-image: url(&quot;../images/i-copy-code.png&quot;); background-repeat: no-repeat; background-position-y: 1px;">Copy Code</span>
|
-|-|
`<span style="color: rgb(0, 128, 0);">// Delete all annotations
</span>page.Annotations.Clear();

<span style="color: rgb(0, 128, 0);">// Delete a particular annotation
</span>page.Annotations.RemoveAt(0);
`|

<p>For more information about how to implement annotations using GcPdf, see [GcPdf sample browser](http://demos.componentone.com/gcdocs/gcpdf/Samples/List#Annotations/code ).</p>[]( )
<div id="i-footer-content" class="i-footer-content" style="padding: 5px 0px 40px; margin-left: 8px; margin-right: 8px; font-size: 0.813em; font-family: &quot;Open Sans&quot;, &quot;Segoe UI&quot;, Verdana, Arial, Helvetica, sans-serif;">
