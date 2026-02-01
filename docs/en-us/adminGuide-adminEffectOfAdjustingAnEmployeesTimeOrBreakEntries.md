---
title: "Effect of adjusting an employee's time or break entries"
id: adminEffectOfAdjustingAnEmployeesTimeOrBreakEntries
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminTrackingMissedBreaksAndAcknowledgingBreaksOmitChunkFromSearchIndex.md
parentSectionTitle: "Tracking missed breaks and acknowledging breaks"
previousSectionFile: adminGuide-adminViewingBreaksInLaborReports.md
previousSectionTitle: "Viewing employee breaks in labor reports"
nextSectionFile: adminGuide-adminEffectOfAutoclockOutOnBreakEntries.md
nextSectionTitle: "Effect of auto-clock out on break entries"
externalReferences: [https://central.toasttab.com/s/article/Editing-Employee-Time-Clock-Entries-1492802387122]
excerpt: "As described in this Toast Central article, it is possible to manually adjust an employee's time entry to modify the start or end time, using the Update Time Entry dialog box."
keywords: [effect,adjusting,employees,time,break,entries]
procedures: 0
codeExamples: 0
---

### Effect of adjusting an employee's time or break entries

As described in this [Toast Central article](https://central.toasttab.com/s/article/Editing-Employee-Time-Clock-Entries-1492802387122), it is possible to manually adjust an employee's time entry to modify the start or end time, using the Update Time Entry dialog box.

![Image](https://doc.toasttab.com/doc/media/breaks-update-time-entry.PNG)

If you manually adjust a time entry, the Toast platform recalculates the time intervals for that time entry and logs missed breaks based on those recalculated time intervals. Consider the following example where an employee's initial time entry was from 8 AM to 4 PM, the time interval for missed break tracking is 4 hours, and the employee logged a break at 11 AM and 2:30 PM. With this scenario, the first time interval is 8 AM to 12 PM and the second time interval is 12 PM to 4 PM and the employee has a break recorded for each interval.

![Image](https://doc.toasttab.com/doc/media/breaks-break-interval-1-taken-interval-2-taken.png)

If the time entry is changed to 7 AM to 3 PM, the new time intervals become 7 AM to 11 AM and 11 AM to 3 PM. To record a break taken during the first break interval, the employee must start the break sometime between 7:00 AM and 10:59 PM and to record a break taken during the second break interval, the employee must start the break sometime between 11 AM and 2:59 PM. Because the employee's first break occurred at 11 AM, which is past the cutoff time for a break to be recorded during the first interval, the first interval no longer has a valid break entry. A missed break for the first interval is logged in the Reports \> Employee performance \> Break entries report. Both the 11 AM and 2:30 PM breaks fall into the second time interval, so that interval has had its break requirement fulfilled.

In the Update Time Entry dialog box, you can also manually create new break entries, using the Add Break button, or modify the start and end time of an existing break by clicking the break entry to access the Update Break dialog box. Toast support does not recommend manually editing breaks. However, if you choose to do so, here are some points to keep in mind:

- The Toast platform will recalculate which break interval a modified break falls into. As such, changes to break entries may result in a break moving from one break interval to another. This can lead to missed breaks getting logged.


- It is not possible to record break acknowledgements for break entries that are entered manually in Toast Web.



If you delete a time entry, using the Deletebutton in the Update Time Entry dialog box, any missed or taken breaks associated with that time entry are also deleted.

