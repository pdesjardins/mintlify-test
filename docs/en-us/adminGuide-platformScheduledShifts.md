---
title: "Scheduled shifts for schedule enforcement"
id: platformScheduledShifts
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformShiftsOverviewOmitChunkFromSearchIndex.md
parentSectionTitle: "Shifts"
previousSectionFile: adminGuide-platformShiftsOverview.md
previousSectionTitle: "Shifts overview"
nextSectionFile: adminGuide-platformShiftsTimeEntriesAndBreaks.md
nextSectionTitle: "Time entries and breaks"
externalReferences: [https://central.toasttab.com/s/article/Enforcing-Scheduling-Time-Clock-Rules-with-Integration-Partners-1492745815961?language=en_US]
excerpt: "A shift is scheduled when you set planned (future) start and end times for it. For example, an integrated scheduling service might create a shift in the..."
keywords: ["scheduled", "shifts", "schedule", "enforcement"]
procedures: 0
codeExamples: 0
---

A shift is *scheduled* when you set planned (future) start and end times for it. For example, an integrated scheduling service might [create a shift in the Toast platform using the Toast labor API](apiDevGuide-apiAddingAShiftAndAssigningIt). The Toast platform stores the expected schedule as a scheduled shift.

You use scheduled shifts as a part of schedule enforcement for employees. When you use schedule enforcement, employees must clock in for shifts within a period of time before and after the scheduled start of the shift. If the employee clocks in outside that time period, the employee must have approval from a manager. For more information about using schedule enforcement, see [this article](https://central.toasttab.com/s/article/Enforcing-Scheduling-Time-Clock-Rules-with-Integration-Partners-1492745815961?language=en_US).

Scheduled shifts are different from shift records for an employee's clocked in work at a location. For more information about shifts for clocked in work in [Shifts overview](adminGuide-platformShiftsOverview).

