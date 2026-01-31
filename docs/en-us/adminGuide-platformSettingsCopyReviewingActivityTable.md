---
title: "Reviewing past copies made using the settings copy feature"
id: platformSettingsCopyReviewingActivityTable
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformSettingsCopyOmitChunkFromSearchIndex.md
parentSectionTitle: "Settings copy feature"
previousSectionFile: adminGuide-platformSettingsCopyCopyingSettings.md
previousSectionTitle: "Copying settings using the settings copy feature"
nextSectionFile: adminGuide-platformPaymentsAndMoneyOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 6. Payments and money"
excerpt: "On the Settings copy page, there is an Activity table that lists historical data for any copies you made for that management group. This table includes the following columns:"
keywords: [reviewing,past,copies,made,settings,copy,feature]
procedures: 0
codeExamples: 0
---

### Reviewing past copies made using the settings copy feature

On the Settings copy page, there is an Activity table that lists historical data for any copies you made for that management group. This table includes the following columns:

- Status: This reflects the status of the copying. There are three possible statuses for your copy instance:

- COMPLETED: The copy completed successfully.



> **Note**
> 
> In instances where a setting must account for a dependent MLM setting, if the setting is copied to a location that is not in the [location hierarchy](ownersAndPermissions.html) used by the dependent setting, the setting is not copied, but will have a COMPLETED status.



- FAILED: The copy failed. Try completing the settings copy again.


- IN PROGRESS: The copy is currently in progress. Wait until the process is complete before starting another settings copy.




- Copied from: The location that the settings were copied from. This is the session restaurant.


- Copied to: The number of locations that the settings were copied to.


- Time: The date and time when the settings were copied.


- Settings: The number of settings that were copied.


- User: The user who copied the settings.



> **Note**
> 
> To use the settings copy feature, you must have the Restaurant Admin > Settings Copy Toolpermission at the locations you are copying from and to.




Select the row to see more details about Copied to and Settings. This lists all locations where the settings were copied to and the individual settings that were copied.

This detailed information is contained to a certain size. If there are additional locations or settings that do not appear initially, select View All at the bottom of the row to see all locations and settings.

Here is an example of the Activity table with one row expanded to show the copied settings.

![The Actitvity table showing past copies on the Settings copy page.](https://doc.toasttab.com/doc/media/mlx-settings-copy-activity-table.png)

