---
title: "Managing job-based access"
id: platformManageJobBasedAccess
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformJobBasedAccessOmitChunkFromSearchIndex.md
parentSectionTitle: "Job-based access"
previousSectionFile: adminGuide-platformJobBasedAccessOverview.md
previousSectionTitle: "Job-based access overview"
nextSectionFile: adminGuide-platformJobBasedAccessOnPOS.md
nextSectionTitle: "Accessing jobs on a Toast POS device"
excerpt: "You enable job-based access on the Access..."
keywords: ["managing", "jobbased", "access"]
procedures: 1
codeExamples: 0
---

You enable job-based access on the **Access management setup** page in Toast Web. To enable job-based access, you must have the **4.25 Enable job-based access** permission enabled at each location in your management group. For more information, see [Access permissions reference](adminGuide-adminPermissions). If you do not have the permission enabled at every location, you can only view the setting in Toast Web. For example, if you have 20 locations in your management group, you must have the **4.25 Enable job-based access** permission enabled to at all 20 locations to update the setting. If you only have the permission enabled at 10 locations, the toggle is grayed out and you cannot update it. 

If you do not have the permission enabled for any of your locations, you cannot access the **Access management setup**page.

**Procedure 4.6. To enable job-based access**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose **Employees &gt; Access management &gt; Access management setup** to open the **Access management setup** page.


3. On the **Access management setup** page, navigate to the **Limit POS permissions to clocked-in job **setting and set the setting to **On**.



> **Note**
> 
> Changes made to the setting affect all locations in your management group.


![Shows the Limit POS permissions to clocked-in job setting in Toast Web.](https://doc.toasttab.com/doc/media/employees-job-based-access.png)


4. Select the **Save** button to save your changes. A confirmation dialog appears notifying you that the change will affect all locations in your management group.

![Shows the confirmation dialog on the Access management setup page in Toast Web.](https://doc.toasttab.com/doc/media/employees-job-based-access-confirmation-dialog.png)


5. Select the **Save** button to continue or the **Cancel** button to cancel out of the confirmation dialog.


6. Choose **Toast account &gt; Publishing &gt; Publish config** to open the **Publish config**page. Publish your changes for each location. For more information, see [Using the Publish Config page](adminGuide-platformHowToPublish#platformPublishingPublishConfigPage).



