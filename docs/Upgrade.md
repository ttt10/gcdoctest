  ---
id: Upgrade  
title: Upgrade to Latest Version
---

To upgrade GcPdf license from v1 to v2, you will obtain a new license key from GrapeCity Sales team. This is a free upgrade for customers who purchased GcPdf v1 license. Once you have received a new license key through email, follow these steps:

1. Open an existing application created using GcPdf v1 license.
2. Right-click the project in Solution Explorer and choose Manage NuGet Packages.
3. In the Package source on top right, select nuget.org.
4. Click Updates tab on the top. A list of all the installed NuGet packages is displayed.
5. On the left panel, select the Select all packages checkbox and click Update.
6. In the Preview Changes dialog, click OK and choose I Accept in the next screen.
7. Switch to the code view and replace the old key with new v2 key received through email.
  - To upgrade the license of a particular instance:  
    >``` var doc = new GcPdfDocument("new key") ```  
  - To upgrade the license of all the instances:  
    >``` GcPdfDocument.SetLicenseKey("new key");```  
