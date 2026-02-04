---
title: "Configuring online ordering hours"
id: adminConfigureOnlineOrderingHoursOverview
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminOnlineOrderingSchedulesOmitChunkFromSearchIndex.md
parentSectionTitle: "Online ordering hours"
previousSectionFile: adminGuide-adminOnlineOrderingScheduleOverview.md
previousSectionTitle: "Online ordering hours overview"
nextSectionFile: adminGuide-adminSettingsForScheduledOrders.md
nextSectionTitle: "Settings for scheduled orders"
externalReferences: [https://central.toasttab.com/s/article/Online-Ordering-Advanced-Settings#leadtime]
excerpt: "The Online ordering hours section displays the online ordering hours for Takeout & Third-party..."
keywords: ["configuring", "online", "ordering", "hours", "Error: could not close current day.", "“Hours cannot pass closeout hour", "which is [hour].”"]
procedures: 3
codeExamples: 0
---

The Online ordering hours section displays the online ordering hours for Takeout & Third-party delivery and First-party delivery. In the Online ordering hours section, the Takeout and Third-party delivery hours are always shown, while First-party delivery hours are only shown if first-party delivery is enabled in Toast Web. To enable first-party delivery, choose Takeout & delivery \> Availability \> Takeout/delivery to open the Takeout/Delivery page.

The following table describes which online ordering hours configuration to use for each ordering channel.

| Online ordering hours | Used for | 
| --- | --- |
| Takeout & Third-party delivery  | - Toast Online Ordering
- Toast Delivery Services (TDS)
- Third-party online ordering channels (for example, Grubhub, DoorDash, and Uber Eats)

 | 
| First-party delivery  | - First-party deliveries

 | 

From the Online ordering hours section, you can open or close your restaurant to online ordering, edit your online ordering hours, and choose to accept orders until closing time.

**Procedure 3.8. To open your restaurant for online ordering**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Takeout & delivery \> Online ordering hours.


3. Select the dining option you want to edit online ordering hours for.


4. Select the day you want the restaurant to be open to online ordering. The setting is set to Closed and the pencil icon is not visible. To open your restaurant for online ordering, toggle the setting from Closed to Open. This opens the Editdialog box.



> **Note**
> 
> If the Toast platform encounters a network problem or too many toggles are applied at once, an error message appears. The error message displays: `Error: could not close current day.
          `The last toggle applied will revert back to its previous position, allowing you to toggle it again. For example, if the error appeared when you toggled the setting from Opento Closed, the toggle would revert back to Open.



5. In the Edit dialog box, add an interval. You can add up to three intervals. An interval is a period of time when online ordering is also available. For example, you can set two intervals if your restaurant is open for online ordering from 11:00 AM-2:00 PM and from 5:00 PM-9:00 PM. The Editdialog box displays the default interval. The default interval is from 9:00 AM-9:00 PM.


6. Edit your hours or select the trash can icon to remove the interval. To add another interval, select the + Add interval button.



> **Note**
> 
> If you have multiple intervals, the intervals cannot overlap and must be in sequential order. For example, you cannot have the first interval from 11:00 AM-12:00 PM, and the second interval from 11:15 AM-11:45 AM, as these intervals overlap. You also cannot have a first interval from 11:00 AM-12:00 PM, and a second interval from 10:15 AM-10:45 AM, as these intervals are not in sequential order. You need to reverse the order, and have the first interval be from 10:15 AM-10:45 AM, and the second interval from 11:00 AM-12:00 PM.



7. Choose the days that the hours apply to and if the hours apply to first-party delivery. If you do not have first-party delivery enabled, you cannot apply the hours to First-party delivery.


8. Select the Update button to update your hours or the Cancel button to close out of the dialog box. Your online ordering hours appear in the Online ordering hours section.


9. Select the Publish all changes button to save and publish your changes. The Confirm Publish dialog box appears. Select the Publish button to publish your changes or the Cancel button to cancel the dialog box.



Online ordering hours can extend past midnight as long as they are before the closeout hour. The closeout hour is the business day cutoff, which is the hour of the day that ends the current business day and starts the next. Allow at least 15 minutes between the end of the online ordering hours and the closeout hour. To configure your closeout hours, contact Toast support.

For example, if the closeout hour is 12:00 AM, your online ordering hours cannot pass 12:00 AM. Your online ordering hours must end at 11:45 AM at the latest. If you try to schedule your online ordering hours past the closeout hour, an error appears in the dialog box. The error message displays: `“Hours cannot pass closeout hour, which is
    [hour].”`

**Procedure 3.9. To close your restaurant for online ordering**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Takeout & delivery \> Online ordering hours.


3. Select the dining option you want to edit online ordering hours for.


4. Select the day you want the restaurant to be closed to online ordering. The setting is set to Open, the online ordering hours are displayed, and the pencil icon is visible. To close your restaurant for online ordering, toggle the setting from Open to Closed.


5. Select the Publish all changes button to save and publish your changes. The Confirm Publish dialog box appears. Select the Publish button to publish your changes or the Cancel button to cancel the dialog box.



**Procedure 3.10. To edit your online ordering hours**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Takeout & delivery \> Online ordering hours.


3. Select the dining option you want to edit online ordering hours for.


4. Select the day you want to edit current hours for. The toggle must be set to Open. Your current online ordering hours are displayed next to the toggle and the pencil icon is visible.


5. Select the pencil icon to open the Edit dialog box. In the Edit dialog box, edit your online ordering hours.


6. Choose the days that the hours apply to and if the hours apply to First-party delivery.


7. Select the Update button to update your hours or the Cancel button to close out of the dialog box. Your online ordering hours appear in the Online ordering hours section.


8. Select the Publish all changes button to save and publish your changes. The Confirm Publish dialog box appears. Select the Publish button to publish your changes or the Cancel button to cancel the dialog box.



### Accepting online orders until closing time

From the Online ordering hours section you can choose to allow guests to place online orders until your restaurant’s closing time. You can choose to allow guests to place orders:

- Until your restaurant’s closing time


- Until your restaurant’s closing time minus the prep time





> **Note**
> 
> This only applies to ASAP orders and not scheduled orders.


| Accept orders until | Example | 
| --- | --- |
| Closing time | In this example: - Your restaurant closes at 10:00 PM.
- Your quote time is 30 minutes.
- Guests can place orders up to 10:00 PM.

A guest places an order at 9:45 PM. The guest’s quote time for their order is 10:15 PM. 

> **Note**
> 
> The closing time does not consider lead times. For more information about lead times, see [Online Ordering: Advanced Settings](https://central.toasttab.com/s/article/Online-Ordering-Advanced-Settings#leadtime).


 | 
| Closing time minus quote time | In this example: - Your restaurant closes at 10:00 PM.
- Your quote time is 30 minutes.
- Guests can place orders up to 9:30 PM.

A guest places an order at 9:30 PM. The guest's quote time for their order is 10:00 PM. For scheduled orders, the last available time slot a guest can place an order is 10:00 PM, as long as the order is placed before 9:30 PM. A scheduled order cannot be placed after 9:30 PM, as Toast Online Ordering will not display time slots after 9:30 PM. | 

Select the Publish all changes button to save and publish your changes. The Confirm Publishdialog box appears. Select the Publish button to publish your changes or the Cancel button to cancel the dialog box.

### Configuring overrides

From the Online ordering hours section you can also add, edit, or remove an override. Scheduled overrides are temporary periods of time (customizable increments of 15 minutes) when a restaurant can adjust their online ordering schedule for a selected date or date range. For example, if your normal operating hours are from 9 AM-9 PM, you can schedule an online ordering override from 1-6 PM every Monday. The override is your restaurant's new online operating hours for Mondays. 

**Procedure 3.11. To add an override**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Takeout & delivery \> Online ordering hours.


3. In the Overrides section, select the + Add override button to open the Add override dialog box.


4. In the Add override dialog box:

- Use the date picker to choose a date for the scheduled override.


- Add an interval for the override or select the Closed all day box. You can set up to three intervals. Select the trash can icon to remove the interval.


- Select which dining behaviors the override applies to. A check mark appears next to the dining option that the override can be applied to. If both dining options are available, you can choose to apply the override to either Takeout & Third-party delivery and/or First-party delivery.



> **Note**
> 
> If you have an override scheduled for a date and a dining option, you cannot schedule another override using the same date and dining option. For example, if you have an override scheduled for May 1, for Takeout & Third-party delivery, you cannot schedule another override for the same date with the same dining option, or both dining options. The Toast platform will display an error message. The error message displays: `This date is
                already taken for the selected Dining option`. However, you can add an override for the same date for First-party delivery. Additionally, if you have a scheduled override that applies to both dining options, you cannot schedule another override for that day.



- Add an optional description for reference purposes. The character limit for the description is 50 characters.




5. Select the Add button to save the override or select the Cancel button to close out of the dialog box.


6. Select the Publish all changes button to save and publish your changes. The Confirm Publish dialog box appears. Select the Publish button to publish your changes or the Cancel button to cancel the dialog box.



**Procedure 3.12. To edit an override**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Takeout & delivery \> Online ordering hours.


3. In the Overrides section, select the pencil icon next to the override to open the Add Override dialog box.


4. In the Add override dialog box, edit the override.


5. Select the Add button to save the override or select the Cancel button to close out of the dialog box.


6. Select the Publish all changes button to save and publish your changes. The Confirm Publish dialog box appears. Select the Publish button to publish your changes or the Cancel button to cancel the dialog box.



**Procedure 3.13. To delete an override**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Takeout & delivery \> Online ordering hours.


3. In the Overrides section, select the trash can icon next to the override you want to delete.


4. Select the Publish all changes button to save and publish your changes. The Confirm Publish dialog box appears. Select the Publish button to publish your changes or the Cancel button to cancel the dialog box.



