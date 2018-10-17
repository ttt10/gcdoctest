---
id: LicenseInformation
title: License Information
---
===================

GrapeCity Documents for PDF supports the following types of license:

-   [Evaluation
    License](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/licenseinfo.html#ev)

-   [No
    License](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/licenseinfo.html#no)

-   [Production
    License](http://help.grapecity.com/gcdocs/gcpdf/onlinehelp/licenseinfo.html#pl)

### Evaluation License

GcPdf evaluation license is available to users for one month to evaluate the
product. If you want to evaluate the product, you can download it and ask for
evaluation license key which is sent to you through mail.

The evaluation version has an expiration date that is determined when an
evaluation key is generated. After applying the evaluation license key, you can
use the complete product until the license expiry date. However, the following
watermark is displayed on the first page of the PDF file:

*'Created with evaluation copy of GrapeCity PDF. Visit www.grapecity.com to
upgrade your license.'*

After the expiry date, the product works with the following limitations:

-   Only 5 pages of the PDF file can be loaded for analyzing.

-   On saving the PDF file, a watermark is displayed on all the pages in that
    file.

Also, following watermark is displayed in the PDF file, once the evaluation
license has expired:

*'Created with expired evaluation copy of GrapeCity PDF. Loading is limited to 5
pages. Visit* [www.grapecity.com](http://www.grapecity.com/) *to purchase
license.'*

### No License

The above mentioned limitations are also imposed when the product is used
without any license.

In such case, following watermark is displayed in the PDF file.

*'Created with unlicensed copy of GrapeCity PDF. Loading is limited to 5 pages.
Visit* [www.grapecity.com](http://www.grapecity.com/) *to purchase license.'*

### Production License

GcPdf production license is issued at the time of purchase of the product. If
you have production license, you can access all the features of GcPdf without
any limitations.

**How to apply Evaluation/Production license in GcPdf**

The key is a long string which needs to be copied to the code in one of the
following two ways.

-   Pass it as an argument to the GcPdfDocument's ctor:  
    `var doc = new GcPdfDocument(key)`  
    This licenses the instance being created.  
      
    

-   Call a static method on GcPdfDocument:  
    `GcPdfDocument.SetLicenseKey(key);`  
    This licenses all the instances while the program is running.
