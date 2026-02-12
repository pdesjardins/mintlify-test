---
title: "Employee clock-in and clock-out"
id: adminOfflineEmployees
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformEmployeesOfflineModeOmitChunkFromSearchIndex.md
parentSectionTitle: "Offline support"
previousSectionFile: adminGuide-platformEmployeesOfflineModeOmitChunkFromSearchIndex.md
previousSectionTitle: "Offline support"
nextSectionFile: adminGuide-platformMultiLocationOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 5. Multiple restaurant locations"
excerpt: "During offline mode, employees can clock in on Toast POS devices and perform many tasks, such as taking orders. Employees may also be able to clock out, depending on whether shift reviews are..."
keywords: ["employee", "clockin", "clockout"]
procedures: 0
codeExamples: 0
---

During offline mode, employees can clock in on Toast POS devices and perform many tasks, such as taking orders. Employees may also be able to clock out, depending on whether shift reviews are required.

The following sections describe configuration settings that affect employee clock outs during offline mode, and the procedures that employees can use to safely start and end their shifts.

## Preparing for offline mode

Two restaurant configuration settings affect how employees can end their shifts:

- The Shift Review option, which you can change. Note that this option only affects clocking out to end a shift, not clocking in to begin a shift.


- The Turn Auto Clock Out On option, which can be changed only by Toast support personnel.



The [Shift Review](adminGuide-adminUiOptionsReference#confShiftReview) option affects how employees can clock out at the end of their shifts:

- Required forces employees to perform a shift review before clocking out. The shift review allows the employee to close out all checks and declare tips. During offline mode, employees cannot clock out of their shifts because shift reviews are not supported in offline mode.


- Optional gives employees the options of performing a shift review and then clocking out, or just clocking out without a shift review. During offline mode, employees can bypass shift reviews and go straight to the clock-out screen.



The Turn Auto Clock Out On option controls the following:

- If enabled (the default), all clocked-in employees are automatically clocked out at the business day cutoff. The business day cutoff is the hour of the day when the restaurant's current business day ends and a new business day begins. Note that the auto-clock-out procedure occurs regardless of the setting of the Shift Review option.


- If disabled, clocked-in employees are never automatically clocked out. The disabled setting is typically used for restaurants that never close, so that employees who are working at the business day cutoff are not clocked out while still working.



Contact Toast support to find out the setting of your restaurant's Turn Auto Clock Out On option or to change it.

## Adjusting time entries

The following procedure explains how to adjust an employee's time entry record. You can use this procedure for an employee who could not clock out during offline mode.

The example in the procedure adjusts the time entry's Out Date field, which was empty because the employee could not clock out.

**Procedure 4.24. To adjust an employee's time entry record**

1. In Toast Web, select Reports \> Employee performance \> Time entries.


2. If necessary, change the View on the Time Entries page to reflect when the employee clocked in and choose Update. For example, change it to Yesterday if the employee clocked in yesterday but you are making the change today.


3. On the Time Entries tab, select the employee name.


4. In the Update Time Entry dialog box, make the adjustment and select Submit.

In the following example, the Out Datefields (which previously were empty) are adjusted to the previous day's date.

![The Update Time Entry dialog box (in the Labor > Time Entry page) for adjusting an employee's Time Entry record.](https://doc.toasttab.com/doc/media/offline-time-entry.png)

As a result, the Out Date, Total Hours, and Payable Hours columns on the Time Entriespage should be updated.



