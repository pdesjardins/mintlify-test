---
title: "Reviewing employee shifts"
id: platformReviewingEmployeeShifts
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformShiftReviewOmitChunkFromSearchIndex.md
parentSectionTitle: "Shift review"
previousSectionFile: adminGuide-platformReopeningAShift.md
previousSectionTitle: "Reopening a shift"
nextSectionFile: adminGuide-performingShiftReviewWhenUsingDeviceGroups.md
nextSectionTitle: "Performing shift review when using device groups"
excerpt: "As a manager, you can review employee shifts on a Toast POS device. To view employee shifts, navigate to Manager Activities, and select Review Employee Shifts to open the Review Employee Shifts..."
keywords: ["reviewing", "employee", "shifts"]
procedures: 0
codeExamples: 0
---



> **Note**
> 
> To access the **Review Employee Shifts** screen, you must have **3. Manager &gt; 3.12 Shift Review**permission. For more information about permissions, see [Manager access permissions](adminGuide-adminPermissions#adminManagerAccessPermissions).


As a manager, you can review employee shifts on a Toast POS device. To view employee shifts, navigate to **Manager Activities**, and select **Review Employee Shifts** to open the **Review Employee Shifts**screen. On the **Review Employee Shifts** screen, employee shifts are separated into either the **Active**or **Closed** category. Active shifts are those where employees are actively taking orders and payments or are in the process of completing shift review. Closed shifts are those where employees have completed shift review and clocked out. The number of active or closed shifts appears to the left of the category name.

On the **Review Employee Shifts** screen, you can view employee shift details, including:

- Status of shift. The status changes based on employee actions.

- **Active shift**: The shift is active. A shift is considered active if the employee has clocked in and added at least one order.


- **Cash collected**: Cash sales have been collected from the employee.


- **Paid out**: Non-cash tips have been paid out and the employee has clocked out.


- **Closed shift**: The shift is closed. A shift is considered closed when all checks are closed, cash tips are declared (if applicable), and the employee has closed the shift.


- **Clocked out**: The employee has clocked out.




- Employee name


- Employee clock-in and clock-out time


- Total payments


- Total cash in hand


- Total non-cash tips



On the **Review Employee Shifts** screen, you can also complete the following actions:

- Search for employees using the **Search**bar


- Filter employee shifts



- View all time cards using the **View time cards** button


- Switch users using the **Switch user**button



## Editing time entries



> **Note**
> 
> To access the **Time entries** panel, you must have **3. Manager &gt; 3.14 Edit Time Entries**permission. For more information about permissions, see [Manager access permissions](adminGuide-adminPermissions#adminManagerAccessPermissions).


You can edit your own shift review or another employee’s using the **Time entries** panel.

![The Time entries panel opened.](https://doc.toasttab.com/doc/media/money-shift-review-time-entries-panel.png)

In the **Time entries **panel, you can complete various actions depending on if the shift is active or closed.

For active shifts, you can:

- View employee shifts


- Complete shift review


- View your job role


- Adjust the start time of today's shift. You cannot adjust the start date of the shift


- Remove the start time. This removes the shift from the Toast platform and any associated reports


- Reset your changes


- Save your changes


- Clock-out of your shift. This opens the **Shift Review** screen where you can complete shift review. This moves the shift from the **Active** category to the **Closed** category



For closed shifts, you can:

- View employee shifts


- Complete shift review


- View your job role


- Adjust the start time of the shift. This reopens the shift and moves the shift from the **Closed** category to the **Active** category


- Adjust the end time of the shift. The updated clock-out time cannot be before the clock-in time and it cannot overlap with another shift


- Remove the start time. This removes the shift from the Toast platform and any associated reports and can affect any cash collected or tips paid out from cash drawers


- Declare or adjust cash tips. Select the **Declare cash tips** button to open a numerical keypad where you can enter a new numerical value or adjust your cash tips. The total declared cash tips appear below the **Declare cash tips** button. For more information, see [Declaring cash tips](adminGuide-platformCompletingShiftReview#platformDeclaringCashTips).

![The Declare cash tips numerical keypad opened.](https://doc.toasttab.com/doc/media/money-shift-review-time-entries-panel-declare-cash-tips.png)


- Reset your changes


- Save your changes



