---
title: "Enabling employee break acknowledgement"
id: adminEnablingEmployeeBreakAcknowledgement
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminTrackingMissedBreaksAndAcknowledgingBreaksOmitChunkFromSearchIndex.md
parentSectionTitle: "Tracking missed breaks and acknowledging breaks"
previousSectionFile: adminGuide-adminEnablingMissedBreakTracking.md
previousSectionTitle: "Enabling missed break tracking"
nextSectionFile: adminGuide-adminViewingBreaksInLaborReports.md
nextSectionTitle: "Viewing employee breaks in labor reports"
externalReferences: [https://central.toasttab.com/s/article/Clocking-In-and-Out-for-Shifts-and-Breaks, https://central.toasttab.com/s/article/Shift-Review-Overview]
excerpt: "When..."
keywords: [enabling,employee,break,acknowledgement]
procedures: 1
codeExamples: 0
---

### Enabling employee break acknowledgement

When you have configured [missed break tracking](adminEnablingMissedBreakTracking.html)for a custom break, the Toast platform tracks when the employee took or missed breaks of that type during their shift. The break acknowledgement feature expands on that functionality by asking the employee, both for taken and missed breaks of that type, whether they were asked to take the break by their manager. An employee is asked for break acknowledgement when:

- The employee clocks back in at the end of a break, using the End Break button on the Time Clock screen.


- The employee clocks out, using the Clock Out button on either the Time Clockscreen or the Shift Review screen.



When either of these activities occur, the Toast platform determines if any of the employee's breaks during the shift so far, either taken or missed, have yet to be acknowledged. For the unacknowledged breaks, the Toast platform presents the employee with the break acknowledgement dialog box, which looks like this if the break was taken:

![Image](https://doc.toasttab.com/doc/media/breaks-acknowledgement-taken.PNG)

If the break was missed, the dialog box look like this:

![Image](https://doc.toasttab.com/doc/media/breaks-acknowledgement-missed.PNG)

Once a break has been acknowledged, the Toast platform logs the employee's response and reports it in the Break entries report, described in [Viewing employee breaks in labor reports](adminViewingBreaksInLaborReports.html). Note that, like missed break tracking, break acknowledgement is enabled on a per custom break basis, so you can request acknowledgement for some breaks and not others. Also note that once a break acknowledgement has been collected, you cannot edit it.

**Procedure 4.22. To enable break acknowledgements**

1. [Log in to Toast Web](adminAccessToastAdminBackend.html).


2. Switch to the restaurant you want to configure.


3. Choose Employees \> Payroll management \> Break types to open the Break types page. You see the Breaks page with a list of the custom breaks you have created.


4. Click the name of a break to see its details page.


5. Under the Advanced Properties section, set the Employee Break Acknowledgement property to Enabled, employees are asked for each break interval if their break was prompted by their manager/employer. Note that this property is only visible if you have set the Track Missed Breaks property to Yes.


6. Click Save and publish your changes.





> **Note**
> 
> See this [Toast Central article](https://central.toasttab.com/s/article/Clocking-In-and-Out-for-Shifts-and-Breaks) for information on clocking out for shifts and breaks. Clocking out may also happen as part of a shift review for employees required to complete one. Shift reviews are described in this [Toast Central article](https://central.toasttab.com/s/article/Shift-Review-Overview).




> **Note**
> 
> Employees who have the Manager \> End Breaks Early permission are presented with the break acknowledgement dialog box even when they end a break early. Employees who do not have the End Breaks Early permission are presented first with the Manager Required: Ending Break Earlydialog box and then with the Break Acknowledgementdialog box. For more information on the End Breaks Early permission, see [Manager access permissions](adminPermissions.html#adminManagerAccessPermissions).


